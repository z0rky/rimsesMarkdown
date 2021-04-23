# Check whether all necessary actions have been executed on the database

$\MAIN\DATABASE\DBSRC\Check_Version_Actions.sql

Open this script with the new or upgraded Rimses database active, using the appropriate query tool, after the entire install/upgrade procedure was completed [1] .
This script will select the last time when each different script was executed on the database with the script-version and the database.

Execute the script to verify whether all necessary scripts have run in the correct order on the database.
Verify the result of this query, compared with the expected install or upgrade scenario.

The following steps must be visible when creating a new version 6.8 database
Extra logging step may also be visible according to the installation scepario.
Action name	
Step sequence

Action date time	Version code	Build nbr
Rimses_Database	Step 1	yyyy-mm-dd hh-mm-ss:hhh	6.8	6.8 yyyy-mm-dd
Rimses SP_Views	Step 2	yyyy-mm-dd hh-mm-ss:hhh	6.8	6.8 yyyy-mm-dd
Rimses triggers	Step 3	yyyy-mm-dd hh-mm-ss:hhh	6.8	6.8 yyyy-mm-dd
Rimses jobs	Step 4	yyyy-mm-dd hh-mm-ss:hhh	6.8	6.8 yyyy-mm-dd
Upload Rimses	Step 5	yyyy-mm-dd hh-mm-ss:hhh	6.8	nnnn
Rimses Ref_int	Step 6	yyyy-mm-dd hh-mm-ss:hhh	6.8	6.8 yyyy-mm-dd


When installing or upgrading a multi-environment, repeat this script on all databases (Master and all environments).

(*) Sql Server Management Studio of the appropriate version; open with the correct database.


