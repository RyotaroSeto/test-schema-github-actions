# public.likes

## Description

## Columns

| Name | Type | Default | Nullable | Children | Parents | Comment |
| ---- | ---- | ------- | -------- | -------- | ------- | ------- |
| user_id | integer |  | false |  | [public.users](public.users.md) |  |
| liked_user_id | integer |  | false |  | [public.users](public.users.md) |  |
| liked_date | timestamp without time zone | CURRENT_TIMESTAMP | false |  |  |  |
| status | integer | 1 | false |  |  |  |
| message_body | varchar(255) |  | true |  |  |  |

## Constraints

| Name | Type | Definition |
| ---- | ---- | ---------- |
| likes_liked_user_id_fkey | FOREIGN KEY | FOREIGN KEY (liked_user_id) REFERENCES users(id) |
| likes_user_id_fkey | FOREIGN KEY | FOREIGN KEY (user_id) REFERENCES users(id) |
| likes_pkey | PRIMARY KEY | PRIMARY KEY (user_id, liked_user_id) |

## Indexes

| Name | Definition |
| ---- | ---------- |
| likes_pkey | CREATE UNIQUE INDEX likes_pkey ON public.likes USING btree (user_id, liked_user_id) |
| likes_user_id_idx | CREATE INDEX likes_user_id_idx ON public.likes USING btree (user_id) |
| likes_liked_user_id_idx | CREATE INDEX likes_liked_user_id_idx ON public.likes USING btree (liked_user_id) |

## Relations

![er](public.likes.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
