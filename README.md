# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization# テーブル設計

## users テーブル

| Column             | Type   | Options                      |
| ------------------ | ------ | -----------                  |
| name               | string | null: false                  |
| email              | string | null: false,unique: true:true|
| encrypted_password | string | null: false                  |
| profile            | text   | null: false                  |
| occupation         | text   | null: false                  |
| position           | text   | null: false                  |

- has_many : comments
- has_many :prototype

## prototypes テーブル

| Column      | Type       | Options                       |
| ------      | ------     | -----------                   |
| title       | string     | null: false                   |
| catch_copy  | string     | null: false                   |
| concept     | text       | null: false                   |
| user        | references | null: false,foreign_key: true |

- belongs_to :user
- has_many : comments

## comments テーブル

| Column       | Type       | Options                        |
| -------      | ---------- | ------------------------------ |
| content      | text       | null: false                    |
| prototype    | references | null: false, foreign_key: true |
| user         | references | null: false, foreign_key: true |

- belongs_to :user
- belongs_to :prototype

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
