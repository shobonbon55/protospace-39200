
## users テーブル

|Column             |type      |Option                           |
|-------------------|----------|---------------------------------|
|email              |string    |null: false, UNIQUE              |
|encrypted_password |string    |null: false,                     |
|name               |string    |null: false,                     |
|profile            |text      |null: false,                     |
|occupation         |text      |null: false,                     |
|position           |text      |null: false,                     |
|


### association
has_many :prototypes
has_many :comment

## prototypes テーブル

|Column             |type       |Option                          |
|-------------------|-----------|--------------------------------|
|title              |string     |null: false                     |
|catch_copy         |text       |null: false                     |
|concept            |text       |null: false                     |
|user               |reference  |null: false, foreign_key: true  |


### association
belongs_to :users
has_many   :comments

## comments テーブル

|Column             |type       |Option                          |
|-------------------|-----------|--------------------------------|
|content            |text       |null: false                     |
|prototype          |reference  |null: false, foreign_key: true  |
|user               |reference  |null: false, foreign_key: true  |

### association
belongs_to :users
belongs_to :prototypes

<!-- 
uma@uma
987654 -->