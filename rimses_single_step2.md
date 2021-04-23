# Step 2: Installation procedure for a new Rimses environment

Install the Rimses program

## Step1: Before you start

When installing Rimses on a Windows server, make sure that the Desktop experience-feature is available

## Step2: Installation of the program Rimses

To start the installation for the default instance of the main Rimses module:

Start the installation on $\MAIN\APPLICATION\EAM\Rimses.msi.

The folder containing the Rimses.msi can also contain a hotfixes folder.
When this is the case, after running the Rimses installation, the Rimses NGen tool will start automatically. This way you can also start the installation of these hotfixes. You only need to check the parameters and press 'Start' to begin the installation.
+ More information regarding the Rimses Ngen tool
Using the installation wizard, you will be able to choose to install optional addons, namely:

Bar-code fonts
Interface module Batch service
Job server
When one of these components is installed, the machine possibly must be restarted. Possibly after this restart, the setup must be relaunched.

When the Rimses job server is installed, the machine where it was installed upon still needs to be configured for the job server to work properly.
Speak to your Rimses contactperson on how you can accomplich this.

You receive further instructions online. (keep the defaults).
To start the installation for a second, third, ... instance:
You cannot and do not need to install the software for a second, third, ... time. You just crete a new shortcut to connect Rimses to another instance.
The Rimses installer created a shortcut. Make a copy of the shortcut.
The shortcut refers to an executable that starts with a default parameter: the instance number. The default instance 01 is added.
Change the instance number in the copied shortcut, the value to 02 for a second, 03 for a third, ... instance.
Continue for the newly created shortcut with the step 'Connect the Rimses program to the database'.

## Step3: Connect the Rimses program to the database

During setup, program items will be added. Select the newly created item Rimses. When you start, the application will detect that it has to be connected.
The following screen (the connection wizard) displays:

Information about the main connection (zone on top of the window):

Database connection:	install	Click on this button in the overview on top to set up the database connection parameters for the targeted environment.
For a multi-environment connection this connection will refer to the master database.
Look in the next section for an explanation on how to enter the database connection colour.
Activate Database Color:	install	Tick this option to use a colour indication for the database connection.
Set Database Color:	install	Click on this button in the overview on top to set up the database connection colour for the targeted environment.
Look in the next section for an explanation on how to set the database connection color
Standard language:	install	Select here another company language for the database.
Information about the parameters (zone 'Parameters' in the middle of the window):

Comment:	This comment will accompany the connection information.
Information about upload execution (Zone 'Upload System tables to database' in the middle of the window):

Execute upload:	When you tick this option, it will trigger the upload of Rimses system data.
This option is automatically disabled:
- if you connect to the application database for the first time.
- if the version of the upload data delivered with the current build is higher than the version of the upload data in the database.
Actual upload version:	The version of the upload data at this moment in the Rimses database.
New upload version:	The version of the upload data delevered with this build.
Information about Environments (Zone on the bottom of the window). DO NOT fill this overview when you are working with a single environment.

Add environment:	install	Click on this button to add an environment to the multi-environment. A new line will be added in the overview.
This button will only become visible when a master environment was specified. It is no longer visible once an multi-environment is in production. "install" />	Click on this button to remove an environment from the multi-environment. The selected environment will be removed from the overview.
This button will only become visible when both a master and child environment were specified. It is no longer visible once a multi-environment is in production.
Code::		This is the unique identification of the environment. It is set by default when creating an environment. It cannot be changed.
Seq Nr:		This integer is used to sort the list of environments throughout the application.
Name::		This is the description of the environment. The name is set by default when you create a new environment but can be changed at any time (ex. Master, Site Belgium, Site France, Site The Netherlands, ...).
Database connection::	install	Click on this button on the bottom to set up the database connection parameterss for the child environment.
look in the next section for an explanation on how to enter the database connection colour.
Standard language:	install	Select here anothe company language for the child environment.
Activate Database Color::	install	Tick this option to use a colour indication for the child database connection.
Set Database Color:	install	Click on this button to set up the database connection colour for the child environment.
Look in the next section for an explanation on how to set up the database connection colour.
Press the Save button when all the parameters are verified and set up correctly. The wizard will start the connection process. Depending on the setting you have made, the program will run the upload program.

When you click on install , the following window displays:

Information about the parameters:

Server:	This is the name or IP address of the machine where the application database is located. You can type the number or name manually or search for the machine. If the server is not displayed, it wasn't detected as a database server for Sql server, or the services for Sql server are not running correctly. (Note : the values '.' or '(local)' refer to the current machine where the application Rimses was started.
User connection (user name and password)::	This is the user that will be used to connect to the application database. The given user must be defined as database owner of the application database and must have the necessary read, write and delete access. Click on Connect to verify server designation, username and password. Next you can select name of the database.
Name database:	This is the name of the database you want the application to connect to.
Click on the Save button when all the connection parameters are verified and set up correctly.
## Step4: User log-on

During the installation or when you start Rimses:

... and no (valid) license is available, the system will ask to insert the license..
... and no user is available to log on, you must define at least one user that has full access in Rimses.

Information::

The icon users is used to link one or more users to the role ADMIN. As soon as at least one user is linked to a role, the icon disappears.
The icon users is used to enter correct licence information. This information is needed to continue in Rimses.
Note in case the type of installation is an UPGRADE from Rimses version 4.8 (or older): from Rimses v5.0 (and higher) on, a new menu structure is provided. The old one will not be converted automatically. Creation of new custom menu layouts is necessary if they existed in the previous version !

## Step5: Load all Rimses assemblies

This step is mandatory for new installations, upgrades and full reinstalls.

Why? To speed up screen startup time, the Rimses assemblies must be pre-loaded by using the RimsesNGen tool.
This tool will make a batch script to execute the Ngen on our Rimses assemblies and preferable execute this script immediately or not.

Follow these steps:
Start the Rimses NGen tool as administrator with "RimsesInstallationFolder>\Tools\RimsesNGenAll.bat".
Fill in the parameters:
Ngen File: Locate the Ngen file locally on your system. Usually, the default location is correct.
Rimses install folder: Choose the root folder where all the assemblies are installed.
Execute Ngen immediately: Execute the batch script immediately after creation.
Attention:
This batch script will take some hours to complete, and it will take a noticable amount of resources (memory and cpu) of the server on which it is executed.
Recomended execution time for this script: a time of low usage of the server.
The default values of these parameters can be configured via "RimsesInstallationFolder>\Tools\RimsesNGen.exe.Config" file.
Press 'Start'
The following actions will be executed in the mentioned order:
The batch script is generated in the folder specified in the 'Rimses install folder' parameter.
When the 'Execute Ngen immediately' parameter was set to 'Yes', the script will be executed and will now take several hours to finish.
When the 'Execute Ngen immediately' parameter was set to 'No', the batch script is not executed.
You can schedule it on a time of your convenience. Run the script as administrator.

Optional: The RimsesNgen tool can be used without user interface by running the "RimsesInstallationFolder>\Tools\RimsesNGen.exe" as administrator with following command-line options:
FILEPATH: The folder thet contains the assemblies to Ngen. Normally this would be the root folder where all the Rimses assemblies are installed.
NGENPATH: The folder that contains the Ngen executable.
Examples:
RimsesNGen.exe "C:\Program Files\RealDolmen\Rimses 6.1"
RimsesNGen.exe "C:\Program Files\RealDolmen\Rimses 6.1" "C:\Windows\Microsoft.NET\Framework64\v4.0.30319\ngen.exe"

Logging:
The execution of both the ngen.bat script and the ngen tool creates a log file where the results of the operation can be verified.
This log file is named RimsesNgenyyyyMMdd>.log and is located in the same folder as the RimsesNgenTool.

## Step6: Configure Rimses Interface Module

### Step 1: Before you start
If integration - based on XML and SOA architecture - with another 3rd party application (Ex.: SAP, AX Dynamics, etc.) is necessary, the Rimses Interface Module must be activated.
(see concept note Concept note Rimses Interface Module).

Verify Microsoft Message Queues: It is possible to import and export data using the Microsoft message queues (MSMQ). If data is exchanged using MSMQ, make sure that you make 'Message queueing' available by adding this Windows-component to all the servers and workstations that will be using the Rimses interface module, online or in batch.


### Step 2a: Configure and activate the Rimses Interface Batch Service
This part of the interface module will launch Rimses at the scheduled times to perform import and/or export tasks.
If this part of the Rimses Interface Module is needed, some extra actions and configurations must be done:

The Rimses installation will have the Windows Batch service in the Rimses installation folder (C:\Program Files\Realdolmen\Rimses X.X) installed.
In the install folder, open the file Rimses.DataInterface.Services.exe.config to configure the service:
Key	Comment
CheckSchedulerInterval	Interval in seconds tor trigger the scheduler
RemotingPort	Port where scheduler object is exposed for remote controlling of the scheduler.
Log	Should there be logging : true or false
LogPath	Path where log files are saved. If you leave this blank, the default logging path. '[Installfolder]\Logging\Rimses Interface Module' is used.
LogFile	Filename for logging actions
SchedulerFile	Filename of the Scheduler log file, containing all scheduled tasks
Start the service Rimses Interface Module Batch Service
### Step 2b: Install, configure and activate the Rimses Interface SOA (Web) Service
This part of the interface module is a web service. Other applications can adress it to do online imports or exports.
Currently this is required for eRimses and the Rimses mobile platform. If this part of the Rimses Interface Module is needed, it needs to be installed and configured:

Start the installation on $\Addon\Rimses Interface Module\Rimses.InterfaceModule.WebService.msi
The setup will start the installation in the folder C:\Program Files (x86)\RealDolmen\Rimses vX.X - Interface Module - WebService
When the setup is done, you should configure IIS to publish this web service:
In the install folder, open the file Web.config for configuring the service:.
Key	Comment
Instance	The id of a valid Rimses Instance (Default 01)
Start the IIS Manager
Create a new Application Pool 'Rimses v6.8' for .Net 4.0 (Integrated)
Create a new Web Site 'Rimses v6.8' that uses this application pool
Create a new Application 'Rimses.WebServices' that maps to the install folder
To test this service, switch to Content View, and browse the RimsesSOA.asmx file, choose the link IsAlive and invoke it. The test is successful when a string is returned containing the current DateTime.
### Step 3: Copying Files
After the installation is done, some files must be copied:

Copy the RimsesConnections.Xml file from a valid Rimses installation to the sub folder bin of the install folder of the web service.
Possibly some criteria files are provided or saved during uninstall. Place the criteria-files in the sub folder Criteria of the install folder of the Rimses application and the web service.
Possibly some transformation files are provided or saved during uninstall. Place the transformation-files in the sub folder Transformations of the install folder of the Rimses application and the web service.
### Step 4: Troubleshooting
If a user in a terminal server session (or Citrix) wants to use the Rimses interface Module, you could get a permission denied error. You can solve this by changing a local security policy (Start > Control Panel > Administrative Tools > Local Security Policy > Local Policies > User Rights Assignment). There you can find a policy Create Global Objects, where you should add a group of users that need access to this feature. For more information, see http://support.microsoft.com/kb/821546/.

## Step7: Install, reinstall or upgrade 

Make sure you are logged on to windows with a user that has sufficient rights:
to grant user or domain group rights
to upload reports onto the SQL reporting server.
to define the desired security settings for the report being installed/upgraded.

Define the user security:
When installing:
make a power user and assign him to the role of system administrator>
grant the report users or a report domain group at least browser access to the reports on SQL reporting services.
When reinstalling, upgrading or patching:
Note down the current security/accessability settings for the affected reports.

Start the installation with $\Addon\Rimses Reporting Services\Publish.bat

In the window that displays:
Verify the parameters:
Report Server Address	Enter the address which users will use to locate reports (e.g. http://MySQLReportServer/reports).
Import from folder	Check if the folder appearing here contains all reporting files needed for install.
Publish to Reporting services	Fill in the folder on which the SQL reports will be published or on which the previously published SQL reports will be replaced
Attention:
- There can be several reporting services folders. This means that this process needs to be repeated for each folder.
- When working with more than one Rimses reporting environment, being a Rimses multi environment or a Rimses test and a production environment) the folder entered here must immediately be correct for the environment for which this install is being done. This means, it cannot be renamed afterwards, e.g. from 'Rimses_Test' to 'Rimses_Prod'
Click 'Go'.
Check the result of the installation in the errors tab.
The reports will be installed on the provided report server address, in the Rimses folder.

Set up/check the connections to the reports datasources:
A new installation will provide new standard data connections which will be used in the reports.
A reinstall or upgrade will not replace the existing standard data sources. It may add new ones.
Open an internet exporer.
Set the adress to the SQL reporting services home page (e.g. http://MySQLReportServer/reports).
Choose the 'Rimses' - 'Data sources' folder.
Hover over each of the data sources to activate the menu arrow and select 'Manage'.
Alter the connection string for each of the data sources
Enter the connection string and also user name and password if necessary
There are 2 types of connection strings:
To a Relational database: Data source=Name Server Database services>;initial catalog=Name Database>
e.g. Data Source=MYSQLSERVER;Initial Catalog=Rimses_PROD
Data source=Name Server Analysis services>;initial catalog=Name Database>;cube='Name cube>'
e.g.: Connection string = "Data source=MySSAS_SERVER;initial catalog=Rimses BI Maintenance;cube='Workorder Management'"
DO NOT alter the name of the datasource, as the Rimses standard SQL reports refer to this name.

Set up the desired security/accessability for the installed reports.
Open an internet exporer.
Set the adress to the SQL reporting services home page (e.g. http://MySQLReportServer/reports).
Choose the 'Rimses' - 'Reports [lang]' folder.
Hover over each of the reports to activate the menu arrow and select 'Manage'.
Set up the availability or distribution of each report by adding subscription and security. Set up the e-mail settings and/or execution account on the reports.
Assign the report users or report domain group to the a role with browser rights to the desired reports or report root folders.

reports for SQL Server Reporting Services
