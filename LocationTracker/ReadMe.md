Geolocation system(https://drive.google.com/file/d/1Nc9692dFWvt5AFvDXvUXzZN9NLoQBX-O/view?usp=sharing)
===================
Tracking location of friends & families.
mobile app sends out current location every x minutes.
users can track their friend's latest & historic locations.
users can set rules to restrict their tracking. e.g. boss can follow monday to friday 9 to 5, wife can follow anytime.

Design api, db schema, system architecture, any other soft app/components

SQL TABLE
---------
users_table
-----------
- use_id, name, pass
- 1, tom, 73hyw
- 2, tom's boss, 73j3hd

followers_table
---------------
- follow_mapping_id, user_id, follows_id
-  1,                 2,        1

rules_table
-----------
- rule_id, follows_mapping_id, weekday, start_time, end_time
- 1,          1,                MONDAY,    09:00,    17:00
- 2,          1,                TUESDAY,    09:00,   17:00
- 3,          1,                FRIDAY,    09:00,   17:00

NO_SQL TABLE
------------
location_table
--------------
- id, user_id, lat, long, time_stamp
- 1,      1,   -26.2, 3.54, 2020-01-01T18:34:00       

active_rules_table
------------------
- user_id, follower_id,  ttl
- 1,       2(tom's boss), 25342        

restricted_location_table
-------------------------
- user_id, follower_id,  location_id
- 1,        2,             1

