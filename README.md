# README

# postテーブル（投稿）
|Column         |Type   |Options    |
|---------------|-------||----------|
|image          |text   ||null:false|placeholderに最高の１枚を！とでも書く
|birdname       |text   ||null:false|
|place          |string ||null:false|
|explain        |text   ||null:false|(1000文字以内)
|user           |reference||forein_key|
### Association
belongs_to :user
has_many   :comments  dependent: :destroy
has_many   :likes  dependent: :destroy

# userテーブル
|Column         |Type   ||Options  |
|---------------|-------||--------|
|name           |string ||null:false|
|image          |text   |アイコン画像
|nickname       |string ||null: false|
|email          |string ||null: false, uniqe: true|
### Association
has_many :posts dependent: :destroy
has_many   :comments  dependent: :destroy
has_many   :likes dependent: :destroy


# commentテーブル
|Column         |Type      ||Options|
|---------------|----------||-------|
|user           |reference ||forein_key|
|text           |string    ||null:false|
|post           |reference ||forein_key|
### Association
belongs_to :user  
belongs_to :post 

# likeテーブル
|Column         |Type   |Options|
|---------------|-------||-------|
|user           |reference ||forein_key|
|post           |reference ||forein_key|
### Association
belongs_to :user  
belongs_to :post  





