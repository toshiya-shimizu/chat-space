# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique: true|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :through:users_groups
- has_many :group through:users_groups
- has_many :through:message

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many :user_groups, through
- has_many :messages, through
- hah_many :user,through : user_groups

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|
|text|text|null: false|
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