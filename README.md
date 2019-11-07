# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|mail|string|null: false|
|passward|string|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :messages
- has_many :groups_users

##　groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|message_id|integer|null: false, foreign_key: true|

### Association
- has_many :users, through: :groups_users
- has_many :messages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user