# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique: true|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :users_groups
- has_many :groups、 through:users_groups
- has_many :messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many :uses_groups
- has_many :messages
- hah_many :through : users_groups

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|
|text|text|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## users_groupsテーブル
 ｜Column|Type|Option|
 |-------|----|------|
 |user_id|integer|null: false, foreign_key: true
 |group_id|integer||null: false, foreign_key: true|
  ### Association
 - belongs_to :group
 - belongs_to :user