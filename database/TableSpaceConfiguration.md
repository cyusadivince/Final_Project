# 📘 **Oracle Tablespace Creation Documentation**

This document describes the creation and configuration of the following tablespaces in Oracle Database 21c:

* **DATA tablespace**
* **INDEX tablespace**
* **TEMPORARY tablespace**
* **AUTOEXTEND management** for datafiles and tempfiles

---

# 🗄️ **1. DATA Tablespace Creation**

```sql
CREATE TABLESPACE data_ts
DATAFILE '\app\CYUSA\product\21c\oradata\data_ts01.dbf'
SIZE 500M
AUTOEXTEND ON NEXT 50M MAXSIZE UNLIMITED;
```

### **Details**

| Attribute       | Value                                          |
| --------------- | ---------------------------------------------- |
| Tablespace name | `data_ts`                                      |
| Initial size    | **500 MB**                                     |
| Autoextend      | +50 MB                                         |
| Maximum size    | Unlimited                                      |
| File path       | `\app\CYUSA\product\21c\oradata\data_ts01.dbf` |

---

# 📁 **2. INDEX Tablespace Creation**

This tablespace stores **indexes**, improving read/query performance and isolating index storage from table storage.

```sql
CREATE TABLESPACE index_ts
DATAFILE '\app\CYUSA\product\21c\oradata\index_ts01.dbf'
SIZE 200M
AUTOEXTEND ON NEXT 20M MAXSIZE UNLIMITED;
```

### **Details**

| Attribute       | Value                                           |
| --------------- | ----------------------------------------------- |
| Tablespace name | `index_ts`                                      |
| Initial size    | **200 MB**                                      |
| Autoextend      | +20 MB                                          |
| Maximum size    | Unlimited                                       |
| File path       | `\app\CYUSA\product\21c\oradata\index_ts01.dbf` |

---

# ❄️ **3. TEMPORARY Tablespace Creation**

The TEMP tablespace is used for sorting, hashing, and global temporary operations.

```sql
CREATE TEMPORARY TABLESPACE temp_ts
TEMPFILE '\app\CYUSA\product\21c\oradata\temp_ts01.dbf'
SIZE 500M
AUTOEXTEND ON NEXT 50M MAXSIZE UNLIMITED;
```

### **Details**

| Attribute       | Value                                          |
| --------------- | ---------------------------------------------- |
| Tablespace name | `temp_ts`                                      |
| Initial size    | **500 MB**                                     |
| Autoextend      | +50 MB                                         |
| Maximum size    | Unlimited                                      |
| File path       | `\app\CYUSA\product\21c\oradata\temp_ts01.dbf` |

---

# 🔧 **4. AUTOEXTEND Configuration (Datafiles + Tempfiles)**

Autoextend ensures datafiles grow automatically as needed.

---

## ✔️ **4.1 Enable Autoextend on TEMPFILE**

```sql
ALTER DATABASE TEMPFILE '\app\CYUSA\product\21c\oradata\temp_ts01.dbf'
AUTOEXTEND ON NEXT 50M MAXSIZE UNLIMITED;
```

---

## ✔️ **4.2 Enable Autoextend on DATA tablespace datafile**

```sql
ALTER DATABASE DATAFILE 'C:\app\CYUSA\product\21c\oradata\DATA_TS01.DBF'
AUTOEXTEND ON NEXT 50M MAXSIZE UNLIMITED;
```

---

## ✔️ **4.3 Enable Autoextend on INDEX tablespace datafile**

```sql
ALTER DATABASE DATAFILE 'C:\app\CYUSA\product\21c\oradata\INDEX_TS01.DBF'
AUTOEXTEND ON NEXT 20M MAXSIZE UNLIMITED;
```

---

## ✔️ **4.4 Enable Autoextend on TEMP tablespace tempfile**

```sql
ALTER DATABASE TEMPFILE 'C:\app\CYUSA\product\21c\oradata\TEMP_TS01.DBF'
AUTOEXTEND ON NEXT 50M MAXSIZE UNLIMITED;
```

---

# 🧪 **5. Verification Commands**

### List all tablespaces

```sql
SELECT tablespace_name, status FROM dba_tablespaces;
```

### Check datafile details

```sql
SELECT file_name, tablespace_name, bytes, autoextensible
FROM dba_data_files;
```
![Chceck datafiles](https://github.com/cyusadivince/RetailFlow-Management-System/blob/main/ScreenShots/database_objects/tablespace1.png)



### Check tempfile details

```sql
SELECT file_name, tablespace_name, bytes, autoextensible
FROM dba_temp_files;
```
![](https://github.com/cyusadivince/RetailFlow-Management-System/blob/main/ScreenShots/database_objects/tablespace2.png)
