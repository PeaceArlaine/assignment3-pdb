
Oracle PDB Tasks

## Problem Statement
This repository contains SQL commands and instructions for creating and managing Oracle Pluggable Databases (PDBs) for class activities.

## Tasks Overview
1. Create a PDB named `plsql_class2024db`.
2. Create another PDB named `ar_to_delete_pdb`, then delete it.
3. Configure Oracle Enterprise Manager and provide a screenshot of the dashboard.

## SQL Queries
1. **Create PDB `plsql_class2024db`**:
   ```sql

CREATE PLUGGABLE DATABASE plsql_class2024db
ADMIN USER ar_plsqlauca IDENTIFIED BY "123"
FILE_NAME_CONVERT = (
    'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\system01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\system01_new.dbf',
    'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\sysaux01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\sysaux01_new.dbf',
    'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\undotbs01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\undotbs01_new.dbf',
    'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\temp01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\temp01_new.dbf'
);

ALTER PLUGGABLE DATABASE plsql_class2024db OPEN;
SHOW PDBS;

2. CREATE PLUGGABLE DATABASE ar_to_delete_pdb 
ADMIN USER ar_plsqlauca 
IDENTIFIED BY 123 
FILE_NAME_CONVERT=('D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\system01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\system01_new.dbf',
    'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\sysaux01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\sysaux01_new.dbf',
    'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\undotbs01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\undotbs01_new.dbf',
    'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\PDBSEED\temp01.dbf', 'D:\SEMESTER_7\PLSQL\ORADATA\ORCL\myPDB\temp01_new.dbf');

ALTER PLUGGABLE DATABASE ar_to_delete_pdb OPEN;

ALTER PLUGGABLE DATABASE ar_to_delete_pdb CLOSE;

DROP PLUGGABLE DATABASE ar_to_delete_pdb INCLUDING DATAFILES;

