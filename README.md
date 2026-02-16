# Oracle Pluggable Database Management Assignment
## Student Information:
•	Name: Divine
•	Student ID: 28796
•	Course: Database Development with PL/SQL (INSY 8311)
•	Instructor: Eric Maniraguha

## Oracle Database Version	[ Oracle Database 19c]
# Task 1: Create a New Pluggable Database
# PDB Details
•	PDB Name: di_pbd_28796
•	Username Created: divine_plsqlauca_28796

## Create PDB
create pluggable database di_pdb_28796 admin user divine_plsqlauca_28796 
identified by 7777
roles=(DBA)
FILE_NAME_CONVERT =('C:\ORACLE19C\ORADATA\ORCL\PDBSEED',
' ORACLE/ORADATA/ORCL/di_pdb_28796');

(screenshots/WhatsApp Image 2026-02-16 at 2.56.22 PM.jpeg)


## opening the pluggable database
ALTER pluggable database di_pdb_28796 open;
ALTER SESSION SET CONTAINER = di_pdb_28796;

screenshots/WhatsApp Image 2026-02-16 at 2.44.33 PM.jpeg

# Task 2: Create and Delete a Temporary PDB
### Temporary PDB Details
•	Temporary PDB Name: di_to_delete_28796

# Create temporary PDB
CREATE pluggable database di_to_delete_28796
admin user divine_plsqlauca_28796 IDENTIFIED by 7777
roles =(DBA)
FILE_NAME_CONVERT =('C:\ORACLE19C\ORADATA\ORCL\PDBSEED',
' ORACLE/ORADATA/ORCL/di_to_delete_28796');

screenshots/WhatsApp Image 2026-02-16 at 2.57.58 PM.jpeg


## Open the temporary PDB
ALTER PLUGGABLE DATABASE di_to_delete_28796 OPEN;


## Close the PDB before dropping
ALTER PLUGGABLE DATABASE di_to_delete_28796 CLOSE IMMEDIATE;

## Drop the PDB including datafiles
DROP PLUGGABLE DATABASE di_to_delete_28796 INCLUDING DATAFILES;
![WhatsApp Image 2026-02-16 at 2 44 35 PM](https://github.com/user-attachments/assets/04df038c-8cda-499f-8ac1-1ef8dd41e73c)


## Verify deletion
SELECT name, open_mode FROM v$pdbs WHERE name = 'di_to_delete_28796';

