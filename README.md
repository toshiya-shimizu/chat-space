# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique: true|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :user_groups
- has_many :group through:user_group
- has_many :message
## groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, foreign_key: true|
### Association
- has_many :user_group
- has_many :message
- hah_many :user, through: users_group
## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|message_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
## user_groupテーブル
 ｜Column|Type|Option|
 |-------|----|------|
 |user_id|integer|null: false, foreign_key: true
 |group_id|integer||null: false, foreign_key: true|
  ### Association
 - belongs_to :group
 - belongs_to :user