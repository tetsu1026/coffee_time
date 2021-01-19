# README

## userテーブル

| Column             | Type   | Options                   |
|--------------------|--------|---------------------------|
| nickname           | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| profile            | string | null: false               |

### Association
has_many :posts
has_many :comments

## postテーブル

| Column             | Type       | Options         |
|--------------------|------------|-----------------|
| shop_name          | string     | null: false     |
| address            | string     | null: false     |
| tel                | string     | null: false     |
| hour               | string     | null: false     |
| regular holiday_id | integer    | null: false     |
| pick_up            | string     |                 |
| brew               | string     |                 |
| explanation        | text       | null: false     |
| user               | references | foreign_key:    |



### Association
belongs_to :user
has_many   :comments

## commentテーブル

| Column             | Type       | Options                   |
|--------------------|------------|---------------------------|
| text               | string     | null: false               |
| user               | references | foreign_key:true          |
| post               | references | foreign_key:true          |

### Association
belongs_to :user
belongs_to :comments
