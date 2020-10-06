# chatspaceのDV設計
# テーブルの追加
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
  has_many :coments
  has_many :groups through: :users_groups

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text| |
|image|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
  belongs_to :user

## users_groups中間テーブル
|Column|Type|Options|
|------|----|-------|
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
 belong_to :user
 belong_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
  has_many :users through: :users_groups