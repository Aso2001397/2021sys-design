```uml
@startuml 
ユーザー -> webサーバー : 商品検索
webサーバー -> DBサーバー : 商品検索照会
DBサーバー -> DBサーバー : 商品検索処理
DBサーバー -> webサーバー : 商品検索結果
webサーバー -> ユーザー : 商品検索結果

activate ユーザー

alt 検索成功
webサーバー -> ユーザー : 商品名を表示
else 検索失敗
webサーバー -> ユーザー : 失敗メッセージを表示
end

deactivate ユーザー
@enduml
```
