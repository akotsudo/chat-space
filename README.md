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
|name|string|null:false|
|e-mail|string|null:false, unique: true|
|password|string|null:false, unique: true|

### Association
- has_many :memebers
- has_many :messages
- has_many :groups, through: :members

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|timestanp|datetime|null: false|

###Association
- belongs_to :group
- belongs_to :user


