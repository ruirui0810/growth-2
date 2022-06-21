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



# テーブル設計

## users テーブル
| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| nickname           | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
### Association
- has_many :tweets
- has_many :comments
- has_many :follows
- has_one :profile


## tweets テーブル
| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| title              | string | null: false               |
| text               | text   | null: false               |
| user               | string | null: false, unique: true |
### Association
- has_many :comments
- belongs_to :user


## comments テーブル
| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| comment            | string | null: false |
| user_id            | string | null: false, unique: true |
| posts_id           | string | null: false |
### Association
- belongs_to :user
- belongs_to :tweet


## profiles テーブル
| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| Column_text        | string | null: false, unique: true |
| user_id            | string | null: false |
### Association
- belongs_to :user


## follows テーブル
| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| follower_id        | string | null: false |
| followee_id        | string | null: false, unique: true |
### Association
- belongs_to :user





# アプリケーション名
目標達成応援アプリ

# アプリケーション概要
目標をシェアし、ユーザー同士で目標達成まで応援し合うことができます。

# URL
https://growth-37335.herokuapp.com/

# テスト用アカウント
・Basic認証パスワード：08101  
・Basic認証ID：ruirui1  
・メールアドレス：  
・パスワード：  

# 利用方法
## 目標投稿
1.トップページのヘッダーからユーザーの新規登録を行います  
2.宣言ボタンから、目標内容を入力・編集ができます  
3.経験値ボタンから、日々の進捗を投稿できます  
## 他者を励ます
1.検索ボタンから、応援したいユーザーを探します  
2.気になるユーザーをフォローすることができます  
3.お気に入りからフォローしたユーザーの投稿が見れます  
4.スタンプボタンから、応援ボタンを選択し、応援できます

# アプリケーションを作成した背景
何か達成したいことがあっても、周りに共有し、応援しあえる仲間がおらず、SNSで仲間を見つけたとしても、コメントのやり取りで時間が取られてしまい、勉強時間がなくなってしまう、という課題を解決したいと思いこのアプリケーションを開発することにしました。

# 洗い出した要件
[要件を定義したシート](https://docs.google.com/spreadsheets/d/170-0l4ts1Si19YSKu0SOEHBon6Snat1clVblrroyYUQ/edit?usp=sharing)

# 実装した機能についての画像やGIFおよびその説明
[![Image from Gyazo](https://i.gyazo.com/fbe3bd6b189877189f3d1168cfb0b3af.gif)](https://gyazo.com/fbe3bd6b189877189f3d1168cfb0b3af)
ログインするとマイページに入れます。

[![Image from Gyazo](https://i.gyazo.com/eeb01c3243eb1f8bd896ff3f835eaf67.gif)](https://gyazo.com/eeb01c3243eb1f8bd896ff3f835eaf67)
今日の経験値から投稿ページに飛ぶことができます。
投稿ページに、今日の成果を入力するとマイページの一番上に表示されます。

# 実装予定機能

# データベース設計
[![Image from Gyazo](https://i.gyazo.com/ec317a73841575dd2eb90dd424631bb2.png)](https://gyazo.com/ec317a73841575dd2eb90dd424631bb2)

# 画面遷移図
[![Image from Gyazo](https://i.gyazo.com/1090d575f9162acd0321b7872d0853b6.png)](https://gyazo.com/1090d575f9162acd0321b7872d0853b6)

# 開発環境
・フロントエンド HTML CSS javascript  
・バックエンド Ruby (Ruby on Rails)  
・開発環境 vscode  
・テスト Ruby