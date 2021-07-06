# DB定義書
## ER図
[ER図はこちら](https://github.com/Aso2001397/2021sys-design/blob/main/ER%E5%9B%B3.md "ER図はこちら")

# DBテーブルカラム詳細一覧
### 購入テーブル (d_purchase)
|和名|属性名(カラム名)|型|PK|NN|FK|
|:---|:---|:---|:---|:---:|:----:|
|オーダーID|order_id|bigint(20)|○|○||
|顧客コード|customer_code|varchar(50)||○||
|購入日|purchase_date|date||○||
|総額|total_price|int(11)||○||

### d_purchase_detail
|属性名|型|PK|NN|FK|
|:---|:---|:---|:---:|:----:|
|detail_id|bigint(20)|○|○||
|detail_id|bigint(20)|○|○|○|
|item_code|int(11)||○||
|price|int(11)||○||
|num|int(11)||○||

### m_customers
|属性名|型|PK|NN|FK|
|:---|:---|:---|:---:|:----:|
|customer_code|varchar(50)|○|○||
|pass|varchar(50)|○|○|○|
|name|varchar(50)||○||
|address|varchar(50)||○||
|tel|varchar(50)||○||
|mail|varchar(50)||○||
|del_flag|int(11)||||
|reg_date|date||○||

### m_category
|属性名|型|PK|NN|FK|
|:---|:---|:---|:---:|:----:|
|category_id|int(11)|○|○||
|name|varchar(20)||○||
|reg_date|date||○||

### m_items
|属性名|型|PK|NN|FK|
|:---|:---|:---|:---:|:----:|
|item_code|int(11)|○|○||
|item_name|varchar(50)||○||
|price|int(11)||○||
|category_id|int(11)||○|○|
|image|varchar(200)||○||
|detail|varchar(500)||||
|del_flag|int(11)||||
|reg_date|date||○||


