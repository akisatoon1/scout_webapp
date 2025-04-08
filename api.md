# backend設計

## 提供するデータ
- 企業の募集
- メッセージ
- インターン生に関する情報
- 企業の情報

## リソース
### 募集リソース
タイトル, 募集要項, 作成日時, 会社名, 会社へのリンク
### 募集一覧リソース
[タイトル, 会社名, 募集へのリンク]

### チャットリソース
属性
#### 会社ユーザー
[メッセージ本文, 作成日時], 学生名, 学生へのリンク
#### 学生ユーザー
[メッセージ本文, 作成日時], 会社名, 会社へのリンク

### チャット一覧リソース
属性
#### 会社ユーザー
[学生名, チャットへのリンク]
#### 学生ユーザー
[会社名, チャットへのリンク]

### メッセージ追加リソース

### 会社リソース
会社名
### 学生リソース
名前
### 学生一覧リソース
[名前, 学生へのリンク]

## api仕様
### 募集
- `GET /recruitments`
- `POST /recruitments`
- `GET /recruitments/{recruitment_id}`

### チャット
- `GET /chats`
- `GET /chats/{chat_id}`
- `POST /chats/{chat_id}/messages`

### 会社
- `POST /companies`
- `GET /companies/{company_id}`

### 学生
- `GET /students`
- `POST /students`
- `GET /students/{student_id}`
