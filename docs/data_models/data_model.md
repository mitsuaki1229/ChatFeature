## users/ユーザー

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| ユーザーID | id | char(36) | Yes | UUID(v4) |
| ユーザー名 | name | varchar(500) | Yes | |
| メールアドレス | email | varchar(300) | Yes | |
| 登録日時 | create_datetime | datetime | Yes | |
| 更新日時 | update_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | id | ユニークキー |

## chat_groups/チャットグループ

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| グループID | id | char(36) | Yes | UUID(v4) |
| グループ名 | name | varchar(500) | Yes | |
| 背景デザインID | background_design_id | char(36) | | |
| BGM ID | background_music_id | char(36) | | |
| 登録日時 | create_datetime | datetime | Yes | |
| 更新日時 | update_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | id | ユニークキー |

## chat_group_members/チャットグループメンバー

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| チャットグループID | chat_group_id | char(36) | Yes | UUID(v4) |
| ユーザーID | user_id | char(36) | Yes | |
| 登録日時 | create_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | chat_group_id,user_id | ユニークキー |

## messages/メッセージ

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| メッセージID | id | char(36) | Yes | UUID(v4) |
| 送信ユーザーID | send_user_id | char(36) | Yes | |
| 受信ユーザーID | received_user_id | char(36) | | |
| 受信チャットグループID | received_chat_group_id | char(36) | | |
| 受信メッセージID | received_message_id | char(36) | | |
| メッセージ | message | varchar(500) | | |
| 画像URL | image_url | varchar(4096) | | |
| スタンプID | stamp_id | char(36) | | |
| 登録日時 | create_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | id | ユニークキー |

## already_read_users/既読ユーザー

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| メッセージID | message_id | char(36) | Yes | |
| ユーザーID | user_id | char(36) | Yes | |
| 登録日時 | create_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | message_id,user_id | ユニークキー |

## reactions/リアクション

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| メッセージID | message_id | char(36) | Yes | |
| ユーザーID | user_id | char(36) | Yes | |
| 種別 | type | enum | Yes | GOOD,HEART_EYES,LAUGHING,RELAXED,COLD_SWEAT,ASTONISHED |
| 登録日時 | create_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | message_id,user_id | ユニークキー |

## notification/通知

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| メッセージID | message_id | char(36) | Yes | |
| 通知種別 | type | enum | Yes | PUSH,EMAIL |
| 登録日時 | create_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | message_id,type | ユニークキー |

## background_designs/背景デザイン

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| 背景デザインID | id | char(36) | Yes | UUID(v4) |
| デザイン名 | title | varchar(500) | Yes | |
| 背景画像 | image | blob | Yes | |
| 登録日時 | create_datetime | datetime | Yes | |
| 更新日時 | update_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | id | ユニークキー |

## background_musics/BGM

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| BGM ID | id | char(36) | Yes | UUID(v4) |
| 曲名 | title | varchar(500) | Yes | |
| 曲 | music | blob | Yes |  |
| 登録日時 | create_datetime | datetime | Yes | |
| 更新日時 | update_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | id | ユニークキー |

## stamps/スタンプ

### エンティティ

| 論理名 | 物理名 | データ型 | Not null | 備考 |
| :--- | :--- | :--- | :--- | :--- |
| スタンプID | id | char(36) | Yes | UUID(v4) |
| スタンプ名 | name | varchar(500) | Yes | |
| 画像 | image | blob | Yes | |
| 登録日時 | create_datetime | datetime | Yes | |
| 更新日時 | update_datetime | datetime | Yes | |

### インデックス

| 名称 | カラム | 備考 |
| :--- | :--- | :--- |
| PRIMARY | id | ユニークキー |
