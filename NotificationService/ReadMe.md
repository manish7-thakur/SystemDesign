Geolocation system(https://drive.google.com/file/d/1Nc9692dFWvt5AFvDXvUXzZN9NLoQBX-O/view?usp=sharing)
===================
Sends notification of the latest news to users.
Sends notification at 7:00, 12:00, 16:00, 20:00.
Users can set their own custom time for notifications.
Breaking news notification is sent to all users.

Design api, db schema, system architecture, any other soft app/components

SQL TABLE
---------
users_table
-----------
- user_id, name, pass
  - 1, tom, 73hyw
  - 2, carl, j3hd

device_table
---------------
- device_id, device_type, device_token, user_id
  - 1,             ios,        73hdh73h,     1
  - 2,             android,    38jsj8j2,     1 

notification_time_table
-----------------------
- config_id, hour, minute, user_id
  - 1,          14,    34,    1
  - 2,          12,    56,    1
  - 3,          7,     23,    2

