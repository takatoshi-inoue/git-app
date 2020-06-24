# chatspace
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
  has_many :comments
  has_many :posts

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text| |
|image|text|null: false|
|tweet_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
  belongs_to :user

## tagsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
### Association
 has_many :posts_tags
 belongs_to :user

## posts_tagsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|post_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
belongs_to :post
belongs_to :tag

