## membersテーブル

|Column|Type|Options|
|------|----|-------|
|members_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
- has_many :message

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|name|string|null: false|

### Association
- has_many :member
- has_many :message

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


