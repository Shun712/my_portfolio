| やりたいこと                     |  HTTPメソッド  | エンドポイント                      | コントローラ#アクション                |
|:---------------------------|:----------:|:-----------------------------|:----------------------------|
| ユーザー登録ページを表示       	       |    GET     | /users/new                   | 	users#new                  |
| ユーザー登録処理                   |    POST    | /users                       | users#create                |
| ユーザー詳細ページを表示               |    GET     | /users/:id                   | users#show                  |
| ログイン画面を表示                  |    GET     | /login                       | user_sessions#new           |
| ログインする                     |    POST    | /login                       | user_sessions#create        |
| ログアウトする                    |   DELETE   | /logout                      | user_sessions#destroy       |
| (本人)ユーザー編集ページを表示           |    GET     | /mypage/account/edit         | mypage/accounts#edit        |
| (本人)ユーザー更新処理               | PUT, PATCH | /mypage/account              | mypage/accounts#update      |
| (本人)ユーザー削除処理               |   DELETE   | /mypage/account              | mypage/accounts#destroy     |
| 作物一覧ページを表示                 |    GET     | /crops                       | crops#index                 |
| 作物登録ページを表示                 |    GET     | /crops/new                   | crops#new                   |
| 作物登録処理                     |    POST    | /crops                       | crops#create                |
| 作物詳細ページを表示                 |    GET     | /crops/:id                   | crops#show                  |
| 作物編集ページを表示                 |    GET     | /crops/:id/edit              | crops#edit                  |
| 作物更新処理                     | PUT, PATCH | /crops/:id                   | crops#update                |
| 作物を削除                      |   DELETE   | /crops/:id                   | crops#destroy               |
| (本人)フォロー一覧ページを表示           |    GET     | /mypage/relationships        | relationships#following     |
| (本人)フォロワ一覧ページを表示           |    GET     | /mypage/relationships        | relationships#follower      |
| ユーザーをフォロー                  |    POST    | /users/:id/relationships     | relationships#create        |
| ユーザーをアンフォロー                |   DELETE   | /users/:id/relationships/:id | relationships#destroy       |
| いいねした一覧ページを表示              |    GET     | /favorites                   | favorites#index             |
| 作物をいいね                     |    POST    | /favorites                   | favorites#create            |
| いいねを解除                     |   DELETE   | /favorites/:id               | favorites#destroy           |
| (本人)予約一覧ページを表示             |    GET     | /mypage/reservations         | mypage/reservations#index   |
| 予約登録ページを表示                 |    GET     | /reservations/new            | reservations#new            |
| 予約登録処理                     |    POST    | /reservations                | reservations#create         |
| 予約詳細ページを表示                 |    GET     | /reservations/:id            | reservations#show           |
| 予約編集ページを表示                 |    GET     | /reservations/:id/edit       | reservations#edit           |
| 予約更新処理                     | PUT, PATCH | /reservations/:id            | reservations#update         |
| 予約を削除                      |   DELETE   | /reservations/:id            | reservations#destroy        |
| (本人)通知一覧を表示                |    GET     | /mypage/notifications        | mypage/notifications#index  |
| チャットルーム登録処理                |    POST    | /chatrooms                   | chatrooms#create            |
| チャットルーム詳細ページを表示            |    GET     | /chatrooms/:id               | chatrooms#show              |
| チャット登録処理                   |    POST    | /chatrooms/:id/chats         | chats#create                |
| チャット更新処理                   | PUT, PATCH | /chats/:id                   | chats#update                |
| チャットを削除                    |   DELETE   | /chats/:id                   | chats#destroy               |
| フィードバック登録ページ表示             |    GET     | /feedbacks/new               | feedbacks#new               |
| フィードバック登録処理                |    POST    | /feedbacks                   | feedbacks#create            |
| 利用規約ページを表示                 |    GET     | /term                        | static_pages#terms          |
| プライバシーポリシーページを表示           |    GET     | /privacy_policy              | static_pages#privacy_policy |
| （管理画面)ユーザー一覧ページを表示       	 |    GET     | /admin/users                 | 	admin/users#index          |
| （管理画面)ユーザー詳細ページを表示       	 |    GET     | /admin/users/:id             | 	admin/users#show           |
| （管理画面)ユーザー編集ページを表示       	 |    GET     | /admin/users/:id/edit        | 	admin/users#edit           |
| （管理画面)ユーザー更新処理             | PUT, PATCH | /admin/users/:id             | admin/users#update          |
| （管理画面）ユーザーを削除する            |   DELETE   | /admin/users/:id             | admin/users#destroy         |
| （管理画面)作物一覧ページを表示       	   |    GET     | /admin/crops                 | 	admin/crops#index          |
| （管理画面)作物詳細ページを表示       	   |    GET     | /admin/crops/:id             | 	admin/crops#show           |
| （管理画面)作物編集ページを表示       	   |    GET     | /admin/crops/:id/edit        | 	admin/crops#edit           |
| （管理画面)作物更新処理               | PUT, PATCH | /admin/crops/:id             | admin/crops#update          |
| （管理画面)作物を削除する              |   DELETE   | /admin/crops/:id             | admin/crops#destroy         |
| （管理画面)予約一覧ページを表示       	   |    GET     | /admin/reservations          | 	admin/reservations#index   |
| （管理画面)予約詳細ページを表示       	   |    GET     | /admin/reservations/:id      | 	admin/reservations#show    |
| （管理画面)予約編集ページを表示       	   |    GET     | /admin/reservations/:id/edit | 	admin/reservations#edit    |
| （管理画面)予約更新処理               | PUT, PATCH | /admin/reservations/:id      | admin/reservations#update   |
| （管理画面)予約を削除する              |   DELETE   | /admin/reservations/:id      | admin/reservations#destroy  |
