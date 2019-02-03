## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :members
- has_many :messages
- has_many :user, through: :memebers

## userテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|name|string|null:false|
|e-mail|string|null:false, unique: true|
|password|string|null:false, unique: true|

### Association
-belongs_to :memebers
-belongs_to :message

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|message_id|integer|null: false, foreign_key: true|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|members_id|integer|null: false, foreign_key: true|
|timestanp|datetime|null: false|

###Association
- has_many :group
- has_many :user
- has_many :members


