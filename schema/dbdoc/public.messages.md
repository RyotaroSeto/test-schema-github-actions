# public.messages

## Description

## Columns

| Name | Type | Default | Nullable | Children | Parents | Comment |
| ---- | ---- | ------- | -------- | -------- | ------- | ------- |
| id | integer | nextval('messages_id_seq'::regclass) | false |  |  |  |
| sender_user_id | integer |  | true |  | [public.users](public.users.md) |  |
| receiver_user_id | integer |  | true |  | [public.users](public.users.md) |  |
| message_body | varchar(255) |  | true |  |  |  |
| status | integer | 1 | false |  |  |  |
| sent_date | timestamp without time zone | CURRENT_TIMESTAMP | false |  |  |  |

## Constraints

| Name | Type | Definition |
| ---- | ---- | ---------- |
| messages_receiver_user_id_fkey | FOREIGN KEY | FOREIGN KEY (receiver_user_id) REFERENCES users(id) |
| messages_sender_user_id_fkey | FOREIGN KEY | FOREIGN KEY (sender_user_id) REFERENCES users(id) |
| messages_pkey | PRIMARY KEY | PRIMARY KEY (id) |

## Indexes

| Name | Definition |
| ---- | ---------- |
| messages_pkey | CREATE UNIQUE INDEX messages_pkey ON public.messages USING btree (id) |
| messages_sender_user_id_idx | CREATE INDEX messages_sender_user_id_idx ON public.messages USING btree (sender_user_id) |
| messages_receiver_user_id_idx | CREATE INDEX messages_receiver_user_id_idx ON public.messages USING btree (receiver_user_id) |

## Relations

![er](public.messages.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
