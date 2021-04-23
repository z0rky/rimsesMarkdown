
# Step 1: Create the Rimses database.

## Step 1.1: Create the database

### 1.1.1 Provide the SQL users

#### 1.1.1.1 The Rimses-Fimacs admin user

This user will be used to create/upgrade all necessary Rimses-Fimacs objects (Database/Jobs/Mail/...).
This can be the sa user of SQL server or a user with sys-admin and server-admin-rights.
When such user cannot be provided, below rights are required.

###### General rights on the server or instance
* SQL-Agent operator
* SQL-Agent reader
* SQL-Agent user
* Database mail user
* SSIS admin (only when using Rimses Analyzer)
* SSIS operator (only when using Rimses Analyzer)

###### Specific rights on the Rimses-Fimacs Database and the Rimses BI database (only when using Rimses Analyzer)
* DDL admin
* Data reader
* Data writer
* The EXECUTE right
* The ALTER right
* The SHOWPLAN right
* The VIEW SERVER STATE right (only when using Fimacs)


#### 1.1.1.2. The Rimses-Fimacs application user

Sapiente iste ducimus itaque ad sed, dolorum, assumenda tempore consequatur quod perspiciatis amet quo ullam dignissimos nisi ratione laboriosam saepe, est debitis autem harum. Excepturi eaque rem culpa cumque saepe.
Quia facere eum itaque voluptatum vero. Amet iste libero fugit, assumenda eius excepturi error nemo, deleniti sed, harum sint! Dicta voluptatibus recusandae accusantium illo deserunt veritatis fugiat, blanditiis aut mollitia.
Iste, tenetur soluta sunt totam neque hic? Optio odit, poss

### 1.1.2 Create a new database

Lorem ipsum dolor, sit amet consectetur adipisicing elit. Iure, minus nisi. Harum, nesciunt doloremque sit ipsa distinctio est laboriosam tempora eum aliquam cumque reiciendis. Excepturi minus accusamus quos modi tempore?
imus veritatis nemo, quas voluptatem ullam aspernatur rem porro delectus nisi nulla itaque. Eum delectus sit et molestiae libero labore inventore.
Iure recusandae voluptates vel amet quae dicta! Sed itaque officia ducimus aspernatur aliquid libero magnam ratione ut? Aperiam, fugiat nihil aspernatur nemo, aliquid provident consequuntur velit odio similique dolor hic.

## Step 1.2: Create the Rimses database structure

$\MAIN\DATABASE\DBSRC\Rimses_Database.sql
Open this script with the newly created Rimses database in active mode, using the appropriate query tool [1] .
This script creates the database tables of Rimses.
Execute the script.

[1] Sql Server Management Studio of the appropriate version; open with the correct database.

## Step 1.3: Create the Rimses database structure

Attention!: All steps described here must be executed sequentially, NOT synchronously

$\MAIN\DATABASE\DBSRC\Rimses_SP_Views.sql:
Open the script using the appropriate query tool[1] and execute it.
This script creates the stored procedures and views that are required to use Rimses.
This script must be executed as a user with one of the following roles or memberships

System administrator
Database owner
Member of the db_owner group of this database
$\MAIN\DATABASE\DBSRC\Rimses_Triggers.sql:
Open the script using the appropriate query tool[1] and execute it.
This script creates the triggers that are required to use Rimses.

$\MAIN\DATABASE\DBSRC\Rimses_Jobs.sql:
Open the script using the appropriate query tool[1] and execute it.
For more information about the server side jobs, see document Information about the Rimses server side jobs.

Note (only for upgraded database):
Triggers that are made by the customer must be created again in the upgraded database structure. It is possible that these triggers are lost during the upgrade.

[1] Sql Server Management Studio of the appropriate version; open with the correct database.

## Step 1.4: Create the Rimses jobs, stored procedures, views and triggers

Check the maintenance plan for the (new) database

When creating a new database, you must create a maintenance plan for it.
When upgrading the database from version 5.7 or older to version 6.0 or higher, a new database will be created. You must create a maintenance plan for this new database.
When upgrading the database from version 6.0 or higher, check whether the current maintenance plan is still valid and take action accordingly.
For more information about how to create a proper maintenance plan, contact the Rimses or Fimacs Helpdesk.

