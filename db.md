# データベース設計
- sqlite3
- 全てnot nullである

## companies
- id         int primary key autoincrement
- user_id    text
- password   text
- name       text
- created_at text
unique(user_id)

## students
- id         int primary key autoincrement
- user_id    text
- password   text
- name       text
- created_at text
unique(user_id)

## chats
- id         int primary key autoincrement
- company_id int foreign key references companies(id)
- student_id int foreign key references students(id)
- created_at text
unique(company_id, student_id)

## messages
- id         int primary key autoincrement
- chat_id    int foreign key references chats(id)
- contents   text
- created_at text

## recruitments
- id         int primary key autoincrement
- company_id int foreign key references companies(id)
- title      text
- contents   text
- created_at text
