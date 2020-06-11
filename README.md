# README
# userテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :chat
- has_many :comments

# chatテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|member|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :comments

# commentテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|chat_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :chat
- belongs_to :user
