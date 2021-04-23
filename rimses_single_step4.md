# Installing addons

## Add-on 1: Integration with Microsoft Project

### Step 1: Verify version of Microsoft Project

Check the Microsoft Project version on the machine (see document Rimses software requirements - Integration with Microsoft Office). Install the required version on the system if necessary.

### Step 2: Information of the standard integration templates

There are two ways to make the MS-Project integration templates available for Rimses:

The templates are copied in '[Rimses Installfolder]\MSProject'.
The user for the MS-Project link must have reading and writing rights on this folder. Should this be a problem, then the location of these templates can be customized by modifying the Rimses general configuration number 344 and copy the templates there.
Template	Comment
PRJTMPlanguage>.MP	Templates to create new individual work orders or work order structures with the capability to upload the context in the application
RIMPRJNEW<:language>.MPT	Templates to create new individual projects or project structures with the capability to upload the context in the application
RIMPRJVIS1language>.MPT	Templates to visualize individual projects or project structures with underlying work orders or work order structures with the capability to upload changed dates in the application
RIMPRJVIS2language>.MPT	Templates to visualize individual projects or project structures with the capability to upload changed dates in the application
RIMTASKSlanguage>.MPT	Templates to visualize individual work orders or work order structures with the capability to upload changed dates in the application
Remark:

Context for Language>

Set value 01 to use  Dutch templates.
Set value 02 to use  French templates.
Set value 03 to use  English templates.
Set value 04 to use  German templates - if applicable.
Set value 06 to use  Spanisch templates - if applicable.



$\MAIN\DATABASE\DBSRC\Rimses_RefInt.sql

Open this script when the new or upgraded Rimses database is active, using the appropriate query tool [1] .
This script defines the internal relationships between the Rimses tables.
Execute the script.

(*) Sql Server Management Studio of the appropriate version; open with the correct database.

## Add-on 2: Integration with barcode scanner

Barcode scanners who communicate with Rimses through the machines COM port (e.g. MC3000 and MC3100)

This feature is only available for the application Rimses. For configuration and setup of the scanner, we refer to the standard online help in Rimses. A barcode scanner is delivered ready to use and in administrative mode. This admin mode is necessary to have access to multiple menu items.

When admin mode is not active, only the menu item '1 DELIV/CORR' is available. Admin mode can be deactivated by de-selecting 'Admin mode' in the option parameters. To reactivate admin mode so that the multiple menus are available again, you can execute the following steps:

Press the 'ESC' button to return to the language menu. The choices '1 NEDERLANDS', '2 FRAN�AIS' and '3 ENGLISH' are visible.
Use the 'ALPHA' button to switch to alphabetic mode.
Press 'CTRL'-'E'.
The welcome window displays, press 'ENTER'
In the language menu, select a language.
All menu items are visible again. Activate the parameters menu and switch on admin mode, to keep the admin mode active.


Barcode scanners who communicate with Rimses using the Rimses SOA webservice

Configure the barcodescanner

## Add-on 3: OCI HookUrl for Rimses and eRimses

This add-on should be installed on a webserver in your network.

It runs under the Microsoft .Net Framework 4.0

The setup is available on $\Addon\Rimses.Web.OCI\setup.exe

This setup will install a web application under IIS at a configurable site (Defaulted to 'Default Web Site') and virtual directory (Defaulted to 'Rimses\OCI').



