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
属性(会社or学生), 学生名, 学生へのリンク, 会社名, 会社へのリンク, [メッセージ本文, 作成日時]

### チャット一覧リソース
属性(会社or学生), [会社名, 学生名, チャットへのリンク]

### メッセージ追加リソース
本文

### 会社リソース
会社名
### 学生リソース
名前
### 学生一覧リソース
[名前, 学生へのリンク]

## api仕様
### 募集
#### `GET /recruitments`
```
[
    {
        "title": "募集のタイトル",
        "company": "会社の名前",
        "link": "募集情報へのurl"
    },
    ...
]
```
#### `POST /recruitments`
reponseは下に同じ
#### `GET /recruitments/{recruitment_id}`
```
{
    "title": "募集のタイトル",
    "": "募集要項",
    "created_at": "作成日時",
    "company": {
        "name": "会社の名前",
        "link": "会社情報へのurl"
    }
}
```

### チャット
#### `GET /chats`
```
{
    "type": "company" or "student",
    "result": [
        {
            "company": "会社名",
            "student": "学生名",
            "link": "チャット情報へのurl"
        },
        ...
    ]
}
```
#### `GET /chats/{chat_id}`
```
{
    "type": "company" or "student",
    "company": {
        "name": "略",
        "link": "略"
    }, 
    "student": {
        "name": "略",
        "link": "略"
    },
    "messages": [
        {
            "content": "メッセージ本文",
            "created_at": "略"
        },
        ...
    ]
}
```
#### `POST /chats/{chat_id}/messages`
```
{
    "content": "略",
    "created_at": "略"
}
```

### 会社
#### `POST /companies`
responseは下に同じ
#### `GET /companies/{company_id}`
```
{
    "name": "略"
}
```

### 学生
#### `GET /students`
```
[
    {
        "name": "略",
        "link": "略"
    },
    ...
]
```
#### `POST /students`
responseは下に同じ
#### `GET /students/{student_id}`
```
{
    "name": "略"
}
```
