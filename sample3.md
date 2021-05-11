```uml
@startuml 
ユーザー -> webサーバー : ログイン
webサーバー -> DBサーバー : ログイン照会
DBサーバー -> DBサーバー : ログイン処理
DBサーバー -> webサーバー : ログイン結果
webサーバー -> ユーザー : ログイン結果

activate ユーザー

alt 検索成功
webサーバー -> ユーザー : ユーザー名を表示
else 検索失敗
webサーバー -> ユーザー : 失敗メッセージを表示
end

deactivate ユーザー

ユーザー -> webサーバー : 商品詳細
webサーバー -> DBサーバー : 商品詳細照会
DBサーバー -> DBサーバー : 商品詳細処理
DBサーバー -> webサーバー : 商品詳細結果
webサーバー -> ユーザー : 商品詳細結果

activate ユーザー

alt 商品詳細成功
webサーバー -> ユーザー : 商品詳細を表示
else 検索失敗
webサーバー -> ユーザー : 失敗メッセージを表示
end

deactivate ユーザー
@enduml
```
