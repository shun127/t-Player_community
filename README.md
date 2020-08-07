# README

## アプリ名
t-Player_community
https://gyazo.com/384a8224061e7957efb18aeb4153b33a
## アプリのURL
http://54.199.15.87/

## テストアカウント
アカウント：test1@gmail.com
パスワード：testtest

## 開発環境
.Ruby
.VSCode(Visual Studio Code)

## 背景
私自身がテニスをしているが相手がおらず中々できないことがあります。
その中で開発したのがt-Player_communityです。
t-Player_communityはコミュニティサイトで周りにいる人とやり取りを
行うことができるサービスです。

# DB設計

## usersテーブル
|Column|Type|Option|
|mail|string|unique: true|
|name|string|null: false, index :true|
|password|string|unique: true|

## Association
has_many :posts
has_many :comments
has_many :likes

## postsテーブル
|user_id|references|null: false, foreign_key: true|
|body|text|

## Association
belongs_to :user
has_many   :comments
has_many   :likes

## likesテーブル
|user_id|references|null: false, foreign_key: true|
|post_id|references|null: false, foreign_key: true|

## Association
belongs_to :user 
belongs_to :post