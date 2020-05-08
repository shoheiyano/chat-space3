## users テーブル

| Column | Type                  | Options     |
| ------ | --------------------- | ----------- |
| name   | string ｜ null: false |
| email  | string                | null: false |

### Association

- has_many :messages
- has_many :groups though: users_groups
- has_many :users_groups

## messages テーブル

| Column   | Type      | Option                        |
| -------- | --------- | ----------------------------- |
| text     | text      | null: false                   |
| image    | string    |                               |
| user_id  | reference | null: false,foreign_key: true |
| group_id | reference | null: false,foreign_key: true |

### Association

- belongs_to :user
- belongs_to :group

## groups テーブル

| Column | Tyoe   | Option      |
| ------ | ------ | ----------- |
| name   | string | null: false |

### Association

- has_many :message
- has_many :users, though: users_groups
- has_many :users_groups

## users_groups テーブル

| Column   | Type      | Option                        |
| -------- | --------- | ----------------------------- |
| user_id  | reference | null: false,foreign_key       |
| group_id | reference | null: false,foreign_key: true |

### Association

- belongs_to :user
- belongs_to :group
