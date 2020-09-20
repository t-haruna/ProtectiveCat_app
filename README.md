## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :billings
- has_many :projects
- has_many :messages


## billingsテーブル
|Column|Type|Options|
|------|----|-------|
|price|int|null: false|
|user_id|integer|null: false, foreign_key: true|
|project_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :project
- belongs_to :user


## projectsテーブル
|Column|Type|Options|
|------|----|-------|
|title|text|null: false|
|image|text|null: false|
|profile|text|null: false|
|text|text|null: false|
|target_amount|int|null: false|
|tarm|data|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- has_many :billings
- belongs_to :user
- has_many :messages


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|project_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :projects
- belongs_to :user
