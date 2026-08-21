mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| collage            |
| dcl                |
| information_schema |
| mysql              |
| performance_schema |
| student            |
| sys                |
+--------------------+
7 rows in set (0.00 sec)

mysql> USE DCL;
Database changed
    mysql> CREATE TABLE MEDICATION(
    -> MED_ID INT PRIMARY KEY,
    -> PAT_ID INT ,
    -> DOSAGE VARCHAR(50));
Query OK, 0 rows affected (0.05 sec)

mysql> DESC MEDICATION;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| MED_ID | int         | NO   | PRI | NULL    |       |
| PAT_ID | int         | YES  |     | NULL    |       |
| DOSAGE | varchar(50) | YES  |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> INSERT INTO MEDICATION VALUES(33,1,"SYRUPS"),(34,2,"TABLETS"),(35,3,"CREAMS");
Query OK, 3 rows affected (0.05 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM MEDICATION;
+--------+--------+---------+
| MED_ID | PAT_ID | DOSAGE  |
+--------+--------+---------+
|     33 |      1 | SYRUPS  |
|     34 |      2 | TABLETS |
|     35 |      3 | CREAMS  |
+--------+--------+---------+
3 rows in set (0.00 sec)

mysql> INSERT INTO MEDICATION(MED_ID,DOSAGE,PAT_ID) VALUES(36,"CAPSULES",4),(37,"DROPS",5),(38,"INJECTIONS",6);
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM MEDICATION;
+--------+--------+------------+
| MED_ID | PAT_ID | DOSAGE     |
+--------+--------+------------+
|     33 |      1 | SYRUPS     |
|     34 |      2 | TABLETS    |
|     35 |      3 | CREAMS     |
|     36 |      4 | CAPSULES   |
|     37 |      5 | DROPS      |
|     38 |      6 | INJECTIONS |
+--------+--------+------------+
6 rows in set (0.00 sec)

mysql>  UPDATE MEDICATION
    -> SET DOSAGE="DROPS"
    -> WHERE MED_ID=33;
Query OK, 1 row affected (0.06 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT * FROM MEDICATION;
+--------+--------+------------+
| MED_ID | PAT_ID | DOSAGE     |
+--------+--------+------------+
|     33 |      1 | DROPS      |
|     34 |      2 | TABLETS    |
|     35 |      3 | CREAMS     |
|     36 |      4 | CAPSULES   |
|     37 |      5 | DROPS      |
|     38 |      6 | INJECTIONS |
+--------+--------+------------+
6 rows in set (0.00 sec)

mysql> UPDATE MEDICATION
    -> SET DOSAGE="TABLETS"
    -> WHERE MED_ID=34;
Query OK, 0 rows affected (0.00 sec)
Rows matched: 1  Changed: 0  Warnings: 0

mysql> SELECT *FROM MEDICATION;
+--------+--------+------------+
| MED_ID | PAT_ID | DOSAGE     |
+--------+--------+------------+
|     33 |      1 | DROPS      |
|     34 |      2 | TABLETS    |
|     35 |      3 | CREAMS     |
|     36 |      4 | CAPSULES   |
|     37 |      5 | DROPS      |
|     38 |      6 | INJECTIONS |
+--------+--------+------------+
6 rows in set (0.00 sec)

mysql> DELETE FROM MEDICATION
    -> WHERE MED_ID=34;
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM MEDICATION;
+--------+--------+------------+
| MED_ID | PAT_ID | DOSAGE     |
+--------+--------+------------+
|     33 |      1 | DROPS      |
|     35 |      3 | CREAMS     |
|     36 |      4 | CAPSULES   |
|     37 |      5 | DROPS      |
|     38 |      6 | INJECTIONS |
+--------+--------+------------+
5 rows in set (0.00 sec)

mysql> DELETE FROM MEDICATION;
Query OK, 5 rows affected (0.01 sec)

mysql> DESC MEDICATION;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| MED_ID | int         | NO   | PRI | NULL    |       |
| PAT_ID | int         | YES  |     | NULL    |       |
| DOSAGE | varchar(50) | YES  |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)

mysql> SELECT * FROM MEDICATION;
Empty set (0.00 sec)

mysql>
mysql> CREATE TABLE HOSP(
    -> MED_ID INT PRIMARY KEY,
    -> PAT_ID INT ,
    -> DOSAGE VARCHAR(50));
Query OK, 0 rows affected (0.09 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| collage            |
| dcl                |
| information_schema |
| mysql              |
| performance_schema |
| student            |
| sys                |
+--------------------+
7 rows in set (0.00 sec)

mysql> SHOW TABLES;
+---------------+
| Tables_in_dcl |
+---------------+
| bank          |
| banks         |
| college       |
| companay      |
| company       |
| dept          |
| emp           |
| hosp          |
| medication    |
| project       |
+---------------+
10 rows in set (0.00 sec)

mysql> DESC EMP;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| EID     | int         | NO   | PRI | NULL    |       |
| ENAME   | varchar(30) | NO   |     | NULL    |       |
| ADDRESS | varchar(50) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM EMP;
+-----+--------+---------+
| EID | ENAME  | ADDRESS |
+-----+--------+---------+
|   1 | SUDEEP | BNG     |
|   2 | ANU    | SND     |
|   3 | REKHA  | SND     |
|   4 | ESHU   | BNG     |
|   5 | MAHESH | HUBBALI |
|   6 | KUSHI  | TUMKURU |
+-----+--------+---------+
6 rows in set (0.00 sec)

mysql> TRUNCATE TABLE EMP;
Query OK, 0 rows affected (0.07 sec)

mysql> CREATE TABLE CUSTOMER(
    -> CID INT PRIMARY KEY,
    -> CNAME VARCHAR(20) NOT NULL,
    -> EMAIL VARCHAR(40) UNIQUE NOT NULL,
    -> PHONE BIGINT UNIQUE NOT NULL CHECK(LENGTH(PHONE)=10));
Query OK, 0 rows affected (0.14 sec)

mysql> CREATE TABLE PRODUCT(
    -> PID INT PRIMARY KEY,
    -> PNAME VARCHAR(30) NOT NULL UNIQUE,
    -> QUANITY INT NOT NULL,
    -> PRICE INT NOT NULL);
Query OK, 0 rows affected (0.13 sec)

mysql> CREATE TABLE ORDERS(
    -> OID INT PRIMARY KEY,
    -> ORDER_TIME TIME,
    -> O_DATE DATE,
    -> CID INT,
    -> PID INT,
    -> FOREIGN KEY (CID) REFERENCES CUSTOMER(CID),
    -> FOREIGN KEY (PID) REFERENCES PRODUCT(PID));
Query OK, 0 rows affected (0.16 sec)

mysql> DESC ORDERS;
+------------+------+------+-----+---------+-------+
| Field      | Type | Null | Key | Default | Extra |
+------------+------+------+-----+---------+-------+
| OID        | int  | NO   | PRI | NULL    |       |
| ORDER_TIME | time | YES  |     | NULL    |       |
| O_DATE     | date | YES  |     | NULL    |       |
| CID        | int  | YES  | MUL | NULL    |       |
| PID        | int  | YES  | MUL | NULL    |       |
+------------+------+------+-----+---------+-------+
5 rows in set (0.00 sec)

mysql> INSERT INTO CUSTOMER VALUES(1,"NAGU","NAGU@GMAI.COM",2345678901),(2,"REKHA","REKU@GMAI.COM",4545454545);
Query OK, 2 rows affected (0.07 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> SRLECT * FROM CUSTOMER;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'SRLECT * FROM CUSTOMER' at line 1
mysql> SELECT *FROM CUSTOMER;
+-----+-------+---------------+------------+
| CID | CNAME | EMAIL         | PHONE      |
+-----+-------+---------------+------------+
|   1 | NAGU  | NAGU@GMAI.COM | 2345678901 |
|   2 | REKHA | REKU@GMAI.COM | 4545454545 |
+-----+-------+---------------+------------+
2 rows in set (0.00 sec)

mysql> DESC PRODUCT;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| PID     | int         | NO   | PRI | NULL    |       |
| PNAME   | varchar(30) | NO   | UNI | NULL    |       |
| QUANITY | int         | NO   |     | NULL    |       |
| PRICE   | int         | NO   |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> INSERT INTO PRODUCT VALUES(1,"COMPUTER",5,50000),(2,"MOBILE",8,40000);
Query OK, 2 rows affected (0.01 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> DESC ORDERS;
+------------+------+------+-----+---------+-------+
| Field      | Type | Null | Key | Default | Extra |
+------------+------+------+-----+---------+-------+
| OID        | int  | NO   | PRI | NULL    |       |
| ORDER_TIME | time | YES  |     | NULL    |       |
| O_DATE     | date | YES  |     | NULL    |       |
| CID        | int  | YES  | MUL | NULL    |       |
| PID        | int  | YES  | MUL | NULL    |       |
+------------+------+------+-----+---------+-------+
5 rows in set (0.00 sec)

mysql> DESC ORDERS;
+------------+------+------+-----+---------+-------+
| Field      | Type | Null | Key | Default | Extra |
+------------+------+------+-----+---------+-------+
| OID        | int  | NO   | PRI | NULL    |       |
| ORDER_TIME | time | YES  |     | NULL    |       |
| O_DATE     | date | YES  |     | NULL    |       |
| CID        | int  | YES  | MUL | NULL    |       |
| PID        | int  | YES  | MUL | NULL    |       |
+------------+------+------+-----+---------+-------+
5 rows in set (0.00 sec)

mysql> INSERT INTO ORDERS VALUES(101,"20:00:00","2026:08:20",1,2),(103,"20:00:00","2026-08-20",1,1),(104,"20:00:00","2026-08-20",2,1);
Query OK, 3 rows affected, 1 warning (0.04 sec)
Records: 3  Duplicates: 0  Warnings: 1

mysql> SELECT *FROM ORDERS;
+-----+------------+------------+------+------+
| OID | ORDER_TIME | O_DATE     | CID  | PID  |
+-----+------------+------------+------+------+
| 101 | 20:00:00   | 2026-08-20 |    1 |    2 |
| 103 | 20:00:00   | 2026-08-20 |    1 |    1 |
| 104 | 20:00:00   | 2026-08-20 |    2 |    1 |
+-----+------------+------------+------+------+
3 rows in set (0.00 sec)
