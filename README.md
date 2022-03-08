# 題材
家庭菜園で作りすぎた作物を近所にお裾分けできるアプリ

# 動機
- 実家で家庭菜園をしているが、作りすぎて余った分は親戚や近所の人にお裾分けしたり、腐って悪くなる前にジャムやソースなどにして加工して保存している。

- 現在はコロナで開催できないが、親戚やその友人を呼んで春と秋にじゃがいも掘りやさつまいも掘りを開催している。その際に他の作物もお土産として参加者に渡している。 

- 作物は時間とともに加工しない限り悪くなってしまうので、近所に欲しい人がいないかマッチングできるようにする。

- 宅配ではなく、消費者が直接取りに行くことで生産者の負担をなくす。

# どんな課題を解決しているか？
- フードロスを減らす

- 処理に困っている人の手助けになる

- 生産者の顔が見える安心

- 地域コミュニティの関係希薄化を改善

# 目的

- 地元地域での相互支援

- 地域単位での自給自足

- 地産地消

- 生産者の顔が見える

# 画面遷移図
https://www.figma.com/file/bCLhhsW8V6k5k5c3SBRGPv/%E3%81%8A%E3%81%99%E3%81%9D%E5%88%86%E3%81%91%E3%82%A2%E3%83%97%E3%83%AA?node-id=0%3A1

# テーブル設計
[![Image from Gyazo](https://i.gyazo.com/6a8d7d0d62ad8cbab3ad813544ae0395.png)](https://gyazo.com/6a8d7d0d62ad8cbab3ad813544ae0395)

## 補足説明

#### サブスク機能
- 生産者は全てのサービスを利用できるが、消費者は作物の予約に関してサブスク登録で利用できる(当面は月額無料)。また、プランは一つしかない予定なのでplansテーブルは設けなかった。

#### 通知機能、リスト化
- 通知機能はポリモーフィックで実装し、フォロー、予約、いいねをしたら通知される。

- フォロー、予約、いいねテーブルはそれぞれリスト一覧としても使う。

- 予約通知は生産者側と消費者側で文言を変える。
```ruby
if current_user.id == @crop.user.id
# 生産者側: 2022年3月8日17:00に消費者へ注文を引き渡す予定です。
else
# 消費者側: 2022年3月8日17:00に生産者から注文を受け取る予定です。
end
```

#### reservationsテーブル
- reservationsテーブルにproducer_idとconsumer_idを分けたがcropとuserが紐づいているのでproducer_idは不要かもしれない。

- 予約時に受け取り希望日時をdateカラムに保存し、チャットで最終的な日時を更新しdate_confirmカラムがtrueになる。

#### cropsテーブル
- GoogleMapAPIを用いて生産者の住所データから座標を特定して、消費者から生産者までのルートを提供する。これを用いて、作物一覧でユーザーに表示されるのは生産者との距離が5km以内の作物に限り表示される。また、生産者までのルートをチャット内でマップ表示できるようにしたいが、実装ができるか未定である。

- 作物の予約が確定されたら、reservedカラムがtrueになり作物一覧から非表示となる。

- チャット内で両者の予定が合わないなどで予約を取り消す場合、reservedカラムがfalseになる。