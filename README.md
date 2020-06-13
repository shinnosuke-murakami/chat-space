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
- has_many :groups_users
- has_many :groups,  through:  :groups_users

# groupsテーブル
|Column|Type|Options|
|------|----|-------|
|grouptitle|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :messages
- has_many :groups_users
- has_many :users,  through:  :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

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
