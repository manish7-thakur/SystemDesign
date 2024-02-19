Messenger app system(https://drive.google.com/file/d/10vL2e9tD6CH0wYfm4vBtqJCzRc1MrQz-/view?usp=sharing)
===================
Sends messages to users on the platform. 100 million daily active users. Each user sends around 100 msg of size 2KB.
Discuss the read/write flow for couples chat and group chat. Discuss strategies for web client to read messages in a
chat.
Design api, db schema, system architecture, any other soft app/components

SQL TABLE
---------
users_table
-----------

| user_id | name  | pass  |
|---------|-------|-------|
| 1       | tom   | 73hyw |
| 2       | carl  | j3hd  |
| 3       | harry | hd74  |

msg_group_table
---------------

| group_id | admin_id(refers user_id) |
|----------|--------------------------|
| 1        | 2                        |
| 2        | 1                        |

group_members_table
---------------

| id | members_group_id(refers group_id) | members_user_id(refers user_id) |
|----|-----------------------------------|---------------------------------|
| 1  | 1                                 | 1                               |
| 2  | 1                                 | 2                               |
| 3  | 1                                 | 3                               |
| 4  | 2                                 | 1                               |
| 5  | 2                                 | 2                               |

NO_SQL TABLE
-------------
messages_table
---------------
search messages by `group_id` (group with most messages will skew read towards a particular shard)

| id | group_id | sender_id(user_id) | context   | timestamp        |
|----|----------|--------------------|-----------|------------------|
| 1  | 2        | 1                  | you suck  | 2024-02-19T14:23 |
| 2  | 1        | 3                  | wtf       | 2024-02-18T15:03 |
| 3  | 2        | 2                  | I'm going | 2024-02-19T14:24 |
