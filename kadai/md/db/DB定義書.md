# DB定義書
## ER図
[ER図はこちら](https://github.com/Aso2001397/2021sys-design/blob/main/ER%E5%9B%B3.md "ER図はこちら")

# DBテーブルカラム詳細一覧
## 購入テーブル (t_purchase)
|和名|属性名(カラム名)|型|PK|NN|FK|
|:---|:---|:---|:---|:---:|:----:|
|購入ID|order_id|bigint(20)|○|○||
|顧客コード|customer_code|varchar(50)||○||
|購入日|purchase_date|date||○||
|総額|total_price|int(11)||○||

## 購入詳細テーブル (t_purchase_detail)
|和名|属性名|型|PK|NN|FK|
|:---|:---|:---|:---|:---:|:----:|
|購入詳細ID|detail_id|bigint(20)|○|○||
|購入ID|detail_id|bigint(20)|○|○|○|
|商品コード|item_code|int(11)||○||
|価格|price|int(11)||○||
|数量|num|int(11)||○||

## 顧客マスタ (m_customers)
|和名|属性名|型|PK|NN|FK|
|:---|:---|:---|:---|:---:|:----:|
|パスワード|pass|varchar(50)|○|○|○|
|氏名|name|varchar(50)||○||
|Eメールアドレス|address|varchar(50)||○||
|電話番号|tel|varchar(50)||○||
|削除フラグ|del_flag|int(11)||||
|登録日|reg_date|date||○||

## カテゴリマスタ (m_category)
|和名|属性名|型|PK|NN|FK|
|:---|:---|:---|:---|:---:|:----:|
|カテゴリID|category_id|int(11)|○|○||
|カテゴリ名|name|varchar(20)||○||
|登録日|reg_date|date||○||

### 商品マスタ (m_items)
|和名|属性名|型|PK|NN|FK|
|:---|:---|:---|:---|:---:|:----:|
|商品コード|item_code|int(11)|○|○||
|商品名|item_name|varchar(50)||○||
|価格|price|int(11)||○||
|カテゴリID|category_id|int(11)||○|○|
|お気に入り|okiniiri_id|varchar(10)||○|○|
|商品画像|image|varchar(200)||○||
|個数選択|kosuu_id|int(11)||||
|商品説明|detail|varchar(500)||||
|削除フラグ|del_flag|int(11)||||
|登録日|reg_date|date||○||
