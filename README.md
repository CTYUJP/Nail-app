# Nailsalon-app（仮）

ネイルサロンを営んでいる知人のお店の予約サイトを作成してみました

## 開発環境

* windows
* Ruby on Rails   7.0.0
* mysql 

## 制作背景

後に記載

# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false |

### Association

has_many :reservation, dependent: :destroy

## reservations テーブル

| Column        | Type       | Options     |
| ------------- | ---------- | ----------- |
| user_id       | references | null: false |
| day           | date       | null: false |
| start_time    | datetime   | null: false |
| end_time      | datetime   | null: false |

### Association

belongs_to :user
