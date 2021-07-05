@startuml tables
entity companies as "companies\n会社" {
  + id [PK]
  --
  name [会社名]
  created_at [作成日]
  updated_at [更新日]
}

entity positions as "positions\n役職マスタ" {
  + id [PK]
  --
  company_id
  name [役職名]
  created_at [作成日]
  updated_at [更新日]
}

entity user_positions as "user_positions\nユーザー役職マスタ関連" {
  + id [PK]
  --
  user_id
  position_id
  created_at [作成日]
  updated_at [更新日]
}

entity users as "users\nユーザー" {
  + id [PK]
  --
  company_id
  login_id [ログインID]
  password [パスワード]
  created_at [作成日]
  updated_at [更新日]
}

entity user_profiles as "user_profiles\nユーザー詳細" {
  + id [PK]
  --
  user_id
  birthday[生年月日]
  name [ユーザー名]
  created_at [作成日]
  updated_at [更新日]
}

entity user_subordinate_users as "user_subordinate_users\nユーザー部下ユーザー関連" {
  + id [PK]
  --
  user_id
  subordinate_user_id [部下ユーザーID]
  password [パスワード]
  created_at [作成日]
  updated_at [更新日]
}

@enduml

@startuml erd
' tables.pu はこのファイルと同じディレクトリに存在している想定です。
!include tables.pu

companies ||-o{ users
companies ||-o{ positions
users ||-o| user_profiles
users ||-o{ user_subordinate_users
users ||-o{ user_positions
positions ||-o{ user_positions
@enduml
