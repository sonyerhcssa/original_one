# アプリケーション名

ORIGINAL_ONE

# アプリケーション概要

webから診察の予約ができます

# URL

未設定

# テスト用アカウント

未設定

# 利用方法

未設定

# アプリケーションを作成した背景

診療所で長時間の診察待ちをした自分自身の経験から、診察待ちを解消できるアプリの制作を考えました。

# 洗い出した要件

要件を定義したシート

# 実装した機能についての画像やGIFおよびその説明

画像やGIF、説明を記載

# 実装予定の機能

カレンダーから直接予約が出来る機能

# データベース設計

[![Image from Gyazo](https://i.gyazo.com/8ad4ca6ace86606bedcc8dc21d2db398.png)](https://gyazo.com/8ad4ca6ace86606bedcc8dc21d2db398)

# 画面遷移図


## users テーブル

| Column             | Type        | Options                        |
| ------------------ | ----------- | ------------------------------ |
| email              | string      | null: false, unique: true      |
| password           | string      | null: false                    |
| first_name         | string      | null: false                    |
| last_name          | string      | null: false                    |
| first_name_kana    | string      | null: false                    |
| last_name_kana     | string      | null: false                    |
| birth_day          | data        | null: false                    |
| phone_number       | string      | null: false                    |
| address            | string      | null: false                    |

### Association
- has_many :reserves


## reserves

| Column             | Type        | Options                        |
| ------------------ | ----------- | ------------------------------ |
| reserve_data       | data        | null: false                    |
| user               | references  | null: false, foreign_key: true |

### Association
- belongs_to :user


## comments テーブル

| Column             | Type        | Options                        |
| ------------------ | ----------- | ------------------------------ |
| comment            | string      | null: false                    |