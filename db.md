# データベース設計
sqlite3

## companies
- id         int pk autoincrement
- user_id    text
- password   text
- name       text
- created_at text

## students
- id         int pk autoincrement
- user_id    text
- password   text
- name       text
- created_at text

## chats
- id         int pk autoincrement
- company_id int
- student_id int
- created_at text

## messages
- id         int pk autoincrement
- chat_id    int
- contents   text
- created_at text

## recruitments
- id         int pk autoincrement
- company_id int
- title      text
- contents   text
- created_at text
