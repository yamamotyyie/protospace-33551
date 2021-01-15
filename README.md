# protospaceテーブル設計

## usersテーブル
|   Column   |  Type  | Options   |
| ---------- | ------ | --------- |
|    email   | string |null: false|
|  password  | string |null: false|
|    name    | string |null: false|
|   profile  |  text  |null: false|
| occupation |  text  |null: false|
|  position  |  text  |null: false|

### Association
- has_many :comments
- has_many :prototypes

## commentsテーブル
|   Column   |    Type   | Options   |
| ---------- | --------- | --------- |
|    text    |    text   |null: false|
|    user    | reference |null: false|
|  prototype | reference |null: false|

### Association
- belong_to :user
- belong_to :prototype

## prototypesテーブル
|   Column   |      Type    | Options   |
| ---------- | ------------ | --------- |
|    title   |    string    |null: false|
| catch_copy |     text     |null: false|
|   concept  |     text     |null: false|
|    user    |  reference   |null: false|

### Association
- has_many :comments
- belong_to :user