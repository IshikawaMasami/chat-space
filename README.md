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
# ChatSpace DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

## messagesテーブル
|Column|Type|Optins|
|------|----|------|
|text|text|
|image|image|
|user_id|integer|null: false|
|group_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル
|Column|Type|Optins|
|------|----|------|
|name|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has-many :users, through: :groups_users

## groups_usersテーブル
|Column|Type|Optins|
|------|----|------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


