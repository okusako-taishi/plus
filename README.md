# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


# plus
## usersテーブル
|culumn|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
|gender|integer|null: false|
|age|integer|null: false|
|profile_image|string||
|profession|string||
|hobby|integer||

### Association
- has_many :reactions
- has_many :chat_rooms, through: :chat_room_users
- has_many :chat_messages

## reactionsテーブル
|culumn|Type|Options|
|------|----|-------|
|to_user_id|integer|null: false|
|from_user_id|integer|null: false|
|status|integer|null: false|

### Association
- belongs_to :user

## chat_roomsテーブル
|culumn|Type|Options|
|------|----|-------|

### Association
- has_many :users, through: :chat_room_users
- has_many :chat_messages

## chat_room_usersテーブル
|culumn|Type|Options|
|------|----|-------|
|chat_room_id|integer|null: false|
|user_id|integer|null: false|

### Association
- belongs_to :user
- belongs_to :chat_room

## chat_messagesテーブル
|culumn|Type|Options|
|------|----|-------|
|chat_room_id|integer|null: false|
|user_id|integer|null: false|
|message|string|null: false|
|image|string||

### Association
- belongs_to :user
- belongs_to :chat_room