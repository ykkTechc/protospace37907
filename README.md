# README

# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
|                    |        | ユニーク制約  |
| encrypted_password | string | null: false |
| name               | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |



### Association

- has_many :prototypes
- has_many :user

## prototypes テーブル

| Column             | Type       | Options     |
| ------------------ | ---------- | ----------- |
| title              | string     | null: false |
| catch_copy         | text       | ユニーク制約  |
| concept            | text       | null: false |
| user               | references | null: false |

### Association

- belongs_to :room_users
- has_many :comments


## comments テーブル
 
| Column             | Type       | Options     |
| ------------------ | ---------- | ----------- |
| content            | text       | null: false |
| prototype          | references | ユニーク制約  |
| user               | references | null: false |

### Association
belongs_to users
belongs_to prototype





