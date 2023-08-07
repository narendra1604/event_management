
Setting environment for using XAMPP for Windows.
karan@PRAVEEN c:\xampp
# mysql.exe -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 14
Server version: 10.4.25-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| amar               |
| dad                |
| information_schema |
| lapak              |
| mysql              |
| nari               |
| performance_schema |
| phpmyadmin         |
| prav               |
| praveen            |
| test               |
+--------------------+
11 rows in set (0.001 sec)

MariaDB [(none)]> create database mom;
Query OK, 1 row affected (0.001 sec)

MariaDB [(none)]> use mom;
Database changed
MariaDB [mom]> create table sathyabama_events(event_id int primary key auto_increment,event_name varchar(90) not null,event_description text,event_date date not null,event_time time not null,venue_id int not null,organizer_id int not null);
Query OK, 0 rows affected (0.021 sec)

MariaDB [mom]> desc sathyabama_events;
+-------------------+-------------+------+-----+---------+----------------+
| Field             | Type        | Null | Key | Default | Extra          |
+-------------------+-------------+------+-----+---------+----------------+
| event_id          | int(11)     | NO   | PRI | NULL    | auto_increment |
| event_name        | varchar(90) | NO   |     | NULL    |                |
| event_description | text        | YES  |     | NULL    |                |
| event_date        | date        | NO   |     | NULL    |                |
| event_time        | time        | NO   |     | NULL    |                |
| venue_id          | int(11)     | NO   |     | NULL    |                |
| organizer_id      | int(11)     | NO   |     | NULL    |                |
+-------------------+-------------+------+-----+---------+----------------+
7 rows in set (0.016 sec)
MariaDB [mom]> create table attendees(attendee_id int primary key auto_increment,attendee_name varchar(90) not null,attendee_email varchar(90) not null unique);
Query OK, 0 rows affected (0.056 sec)

MariaDB [mom]> desc attendee;
ERROR 1146 (42S02): Table 'mom.attendee' doesn't exist
MariaDB [mom]> desc attendees;
+----------------+-------------+------+-----+---------+----------------+
| Field          | Type        | Null | Key | Default | Extra          |
+----------------+-------------+------+-----+---------+----------------+
| attendee_id    | int(11)     | NO   | PRI | NULL    | auto_increment |
| attendee_name  | varchar(90) | NO   |     | NULL    |                |
| attendee_email | varchar(90) | NO   | UNI | NULL    |                |
+----------------+-------------+------+-----+---------+----------------+
3 rows in set (0.036 sec)

MariaDB [mom]> create table organizers(organizer_id int primary key auto_increment,organizer_name varchar(90) not null,organizer_email varchar(90) not null);
Query OK, 0 rows affected (0.045 sec)

MariaDB [mom]> desc organizers;
+-----------------+-------------+------+-----+---------+----------------+
| Field           | Type        | Null | Key | Default | Extra          |
+-----------------+-------------+------+-----+---------+----------------+
| organizer_id    | int(11)     | NO   | PRI | NULL    | auto_increment |
| organizer_name  | varchar(90) | NO   |     | NULL    |                |
| organizer_email | varchar(90) | NO   |     | NULL    |                |
+-----------------+-------------+------+-----+---------+----------------+
3 rows in set (0.035 sec)

MariaDB [mom]> create  table venues(venue_id int primary key auto_increment,venue_name varchar(90) not null,venue_mail varchar(90) not null);
Query OK, 0 rows affected (0.048 sec)

MariaDB [mom]> desc venues;
+------------+-------------+------+-----+---------+----------------+
| Field      | Type        | Null | Key | Default | Extra          |
+------------+-------------+------+-----+---------+----------------+
| venue_id   | int(11)     | NO   | PRI | NULL    | auto_increment |
| venue_name | varchar(90) | NO   |     | NULL    |                |
| venue_mail | varchar(90) | NO   |     | NULL    |                |
+------------+-------------+------+-----+---------+----------------+
3 rows in set (0.017 sec)

MariaDB [mom]> create table event_registrations(registration_id int primary key auto_increment,event_id int not null,
    -> attendee_id int not null,registration_date timestamp default current_timestamp);
Query OK, 0 rows affected (0.049 sec)

MariaDB [mom]> desc event_registrations;
+-------------------+-----------+------+-----+---------------------+----------------+
| Field             | Type      | Null | Key | Default             | Extra          |
+-------------------+-----------+------+-----+---------------------+----------------+
| registration_id   | int(11)   | NO   | PRI | NULL                | auto_increment |
| event_id          | int(11)   | NO   |     | NULL                |                |
| attendee_id       | int(11)   | NO   |     | NULL                |                |
| registration_date | timestamp | NO   |     | current_timestamp() |                |
+-------------------+-----------+------+-----+---------------------+----------------+
4 rows in set (0.047 sec)

MariaDB [mom]>
