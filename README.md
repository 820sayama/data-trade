# README

# users テーブル

| Column             | Type           | Options                      |
| ------------------ | ------------   | --------------------------   |
| email              | string         | null: false,unique: true     |
| encrypted_password | string         | null: false                  |
| nickname           | string         | null: false                  |

has_many :orders
has_many :items

# itemsテーブル

| Column             | Type           | Options                      |
| ------------------ | ------------   | --------------------------   |
| product            | string    　　    | null: false                |
| price              | integer   　　  | null: false                  |
| explanation        | text       　 　| null: false                  |
| user               | references     | null: false,  foreign_key   　|

belongs_to :user
has_one :order

# ordersテーブル

| Column             | Type           | Options                      |
| ------------------ | ------------   | --------------------------   |
| user               | references     | null: false,foreign_key: true|
| item               | references     | null: false ,foreign_key:true|          

belongs_to :user
belongs_to :item