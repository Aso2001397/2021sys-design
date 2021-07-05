```startuml
@startuml
    entity "顧客マスタ" as customer <m_customers>{
        + customer_code [PK]
        --
        pass
        name
        address
        tel
        mail
        del_flag
        reg_date
    }
@enduml
```

```startuml
@startuml
    entity "購入テーブル" as customer <d_purchase>{
        + order_id [PK]
        --
        + customer_code[FK]
        purchase_date
        total_price
    }
@enduml
```

```startuml
@startuml
    entity "購入詳細テーブル" as customer <d_purchase_detail>{
        + order_id[PK]
        + detail_id[PK]
        --
        + item_code[FK]
        price
        num
    }
@enduml
```

```startuml
@startuml
    entity "商品マスタ" as customer <m_items>{
        + item_code [PK]
        --
        item_name
        price
        + category_id[FK]
        image
        detail
        del_flag
        reg_date
    }
@enduml
```

```startuml
@startuml
    entity "カテゴリマスタ" as customer <m_category>{
        + category_id [PK]
        --
        name
        reg_date
    }
@enduml

```startuml
@startuml
-companies ||-o{ users
+companies ||-d-o{ users
 companies ||-o{ positions
-users ||-o| user_profiles
-users ||-o{ user_subordinate_users
+users ||-l-o| user_profiles
+users ||-d-o{ user_subordinate_users
 users ||-o{ user_positions
 positions ||-o{ user_positions
 
 @enduml
 ```
