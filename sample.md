```uml
@startuml 
webサーバー -> DBサーバー : 商品検索照会
DBサーバー -> DBサーバー : 商品検索処理
DBサーバー -> webサーバー : 商品検索結果
@enduml
```
