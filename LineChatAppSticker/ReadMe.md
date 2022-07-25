Line sticker chat system(https://drive.google.com/file/d/1Nc9692dFWvt5AFvDXvUXzZN9NLoQBX-O/view?usp=sharing)
===================
Users can send stickers to their friends.
A user can send only the stickers which they have purchased.
Users can see all stickers whether purchased or not.

Design api, db schema, system architecture, any other soft app/components

SQL TABLE
---------
users_table
-----------
- user_id, name, pass
  - 1, tom, 73hyw
  - 2, tom's boss, 73j3hd

packages_table
---------------
- id, name, price_usd
  - 1, bunny_bear, 20    1
  - 2, stars, 25

purchased_packages_table
---------------
- id, package_id, user_id
  - 1,       2,    1
  - 2,       2,    2

NO_SQL TABLE
------------
messages_table
--------------
- id, from_id, to_id, msg_type, text, sticker_id, image_url time_stamp
  - 1, 2, 1, 2, sticker, null, 23, null, 2020-01-01T18:34:00
  - 2, 1, 2, 1, text, you suck, null, null, 2020-01-01T18:34:00
  - 2, 1, 2, 1, image, null, null, aws:hkg:/root/someblob, 2020-01-01T18:34:00