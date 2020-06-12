’’’README
# usersテーブル
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :groups
- has_many :messages

# groupsテーブル
|Column|Type|Options|
|------|----|-------|
|grouptitle|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- has_many :messages
- has_many :groups_menbers
- has_many :menbers,  through:  :groups_menbers

## menbersテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
### Association
- has_many :groups_menbers
- has_many  :groups,  through:  :groups_menbers

## groups_menbersテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|menber_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :menber

# messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|body|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
