---
title: "Oracle"
tags:
-   tools
---

### Export a database dump  
```shell
exp <user>/<password>@<pluggableDB>
buffer size: 4096 >
export file: EXPDAT>DMP > myDump.dmp
(1) Entire database (2) Users, or (3)Tables : (2)Users >
Export grants (yes/no): yes >
Export table data (yes/no): yes >
Compress extents (yes/no): yes >
Export done in WE8MSWIM1252 character set...
User to be exported: (RETURN to quit) > schema_user
exporting...
```

### Create a new pluggable database (oracle 21c)  
```shell

sqlplus / as sysdba

CREATE PLUGGABLE DATABASE salespdb
  ADMIN USER salesadm IDENTIFIED BY password
  ROLES = (dba)
  DEFAULT TABLESPACE sales
    DATAFILE '/disk1/oracle/dbs/salespdb/sales01.dbf' SIZE 250M AUTOEXTEND ON
  FILE_NAME_CONVERT = ('/disk1/oracle/dbs/pdbseed/',
                       '/disk1/oracle/dbs/salespdb/')
  STORAGE (MAXSIZE 2G)
  PATH_PREFIX = '/disk1/oracle/dbs/salespdb/';
```

### List pluggable databases  
```shell
COLUMN NAME FORMAT A8

SELECT NAME, CON_ID, DBID, CON_UID, GUID FROM V$CONTAINERS ORDER BY CON_ID;
```

### Show open mode status of pluggable databases  
```shell
COLUMN NAME FORMAT A15
COLUMN RESTRICTED FORMAT A10
COLUMN OPEN_TIME FORMAT A30
SELECT NAME, OPEN_MODE, RESTRICTED, OPEN_TIME from V$PDBS;
```

### change pdb to READ WRITE  
```shell
ALTER PLUGGABLE DATABASE XEPDB4 OPEN READ WRITE;
```

### save pdb state so you don't have to manually open
```shell
ALTER PLUGGABLE DATABASE XEPDB4 SAVE STATE;
```

### deleting a pluggable database  
```shell
sqlplus / as sysdba

alter pluggable database XEPDB4 close;
drop pluggable database XEPDB4 including datafiles;
```

### switching session container  
```shell
show con_name
alter session set container = mypdb2;
show con_name
```

### check oracle 21 xe pdb data usage

```
SELECT pdb_name, used_bytes/1024/1024/1024 "Used GB", 
       max_bytes/1024/1024/1024 "Max GB" 
FROM cdb_pdbs, 
     (SELECT con_id, sum(bytes) used_bytes 
      FROM   cdb_segments 
      WHERE  con_id > 2 
      GROUP BY con_id) seg_used, 
     (SELECT con_id, max(bytes) max_bytes 
      FROM   cdb_data_files 
      WHERE  con_id > 2 
      GROUP BY con_id) df_max 
WHERE  cdb_pdbs.con_id = seg_used.con_id(+) 
AND    cdb_pdbs.con_id = df_max.con_id(+);
```

