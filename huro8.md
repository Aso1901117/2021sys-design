```uml
@startuml
opt　未登録
ユーザー->webサーバー:ユーザー登録
webサーバー->DBサーバー:ユーザー登録
DBサーバー->DBサーバー:登録処理
DBサーバー->webサーバー登録結果

alt 登録成功
webサーバー->ユーザー:登録メッセージを表示
else　登録失敗
webサーバー->ユーザー:失敗メッセージを表示

end
end
```uml
@startuml
ユーザー->webサーバー:ログイン
webサーバー->DBサーバー:ログイン参照
DBサーバー>DBサーバー:ログイン処理
DBサーバー->webサーバー:認証結果

activateユーザー
opt 認証成功
webサーバー->ユーザー:ユーザー名を表示
else 認証失敗
webサーバー->ユーザー:失敗メッセージを表示
end
opt ログイン中
ユーザー->webサーバー:ログアウト
webサーバー->DBサーバー:ログアウト参照
DBサーバー>DBサーバー:ログアウト処理
DBサーバー->webサーバー:ログアウト結果
webサーバー->ユーザー:ログアウト結果
end

deactivateユーザー
@enduml
```
