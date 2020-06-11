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
- has_many :chat_tags
- has_many :tags,  through:  :chat_tags

## tagsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
### Association
- has_many :chat_tags
- has_many  :chat,  through:  :chat_tags

## chat_tagsテーブル
|Column|Type|Options|
|------|----|-------|
|chat_id|integer|null: false, foreign_key: true|
|tag_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :chat
- belongs_to :tag

# commentテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|chat_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :chat
- belongs_to :user
