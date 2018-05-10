---
TOCTitle: Migrating from Windows Internal Database to SQL Server 2005
Title: Migrating from Windows Internal Database to SQL Server 2005
ms:assetid: 'b4852133-5ed3-48d7-8a95-e7866e638c18'
ms:contentKeyID: 18132499
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc708558(v=WS.10)'
---

Migrating from Windows Internal Database to SQL Server 2005
===========================================================

This topic explains how to migrate the WSUS database (SUSDB) from a Windows Internal Database instance (installed by default during WSUS setup) to a full version of Microsoft SQL Server 2005.

Reasons to migrate the WSUS database to SQL Server 2005
-------------------------------------------------------

-   If you chose to use Windows Internal Database as the WSUS database when you set up your WSUS server, you may want to upgrade the database engine to a full installation of SQL Server 2005. SQL Server 2005 allows you to administer the WSUS database through the SQL Server Management Studio.

SQL Server 2005 database requirements
-------------------------------------

-   WSUS requires SQL Server 2005 with Service Pack 1. If you use the full version of SQL Server, the database administrator should first verify that the nested triggers option is turned on before setting up the WSUS database.
-   You cannot use SQL authentication. WSUS supports Windows authentication only. WSUS setup creates a database named SUSDB.

Scenarios
---------

The following scenarios are presented in this topic:

-   Migrating the Windows Internal Database database to a SQL Server 2005 instance running on the WSUS server
-   Migrating the Windows Internal Database database to a SQL Server 2005 instance running on another server (remote SQL)

#### Migrating the WSUS database from a Windows Internal Database instance to a SQL Server 2005 instance running on the WSUS server

Use the following steps to migrate the WSUS database from a Windows Internal Database instance to a SQL Server 2005 instance.

1.  Install SQL Server 2005 (with the **Server and Client Tools** option) and SQL Server 2005 Service Pack 1 or higher on your WSUS server.
2.  Stop the **IIS Admin** service and the **Update Services** service:
    -   Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Services**.
    -   Right-click **IIS Admin Service**, and then click **Stop**.
    -   Right-click **Update Services**, and then click **Stop**.

1.  Attach **SUSDB** to the destination SQL instance.
    -   In SQL Server Management Studio, under the instance node, right-click **Databases**, select **Properties**, and then click **Attach**.
    -   In the **Attach Databases** box, under **Databases to attach**, browse to the location of the susdb.mdf file (by default this is **C:\\WSUS\\UpdateServicesDbFiles** if you installed Windows Internal Database), and then click **OK**.
2.  Verify that NT AUTHORITY\\NETWORK SERVICE has login permissions to the SQL Server instance and to the WSUS database. If it does not, you will need to add it to both locations. This account should also be a member of the webService role on the WSUS database.
    -   Verify permissions on the SQL Server instance. In SQL Server Management Studio, open the instance and select **Security**, then **Logins**. The NT AUTHORITY\\NETWORK SERVICE account should be listed as a login. If it is not, it should be added.
    -   Verify permissions on the database. Right-click the database, select **Properties** and then click **Permissions**. The NT AUTHORITY\\NETWORK SERVICE account should be listed as a login. If it is not, it should be added.
    -   Verify members of the webService role. Under the WSUS database, select Roles, then right-click webService and select Properties. The NT AUTHORITY\\NETWORK SERVICE account should be listed as a member of this role. If it is not, it should be added.
3.  Edit the registry to point WSUS to the SQL instance that now holds SUSDB.
    -   Click **Start**, click **Run**, type **regedit**, and then click **OK**.
    -   Find the following key: **HKLM\\SOFTWARE\\Microsoft\\UpdateServices\\Server\\Setup\\SqlServerName**, and in the **Value** box, type **\[ServerName\]\\\[InstanceName\]**,and then click **OK**. If the instance name is the default instance, then simply type **\[ServerName\].**
4.  Open **Services** and then start the **IIS Admin** service and **Update Services** service.
    -   Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Services**.
    -   Right-click **IIS Admin Service**, and then click **Start**.
    -   Right-click **Update Services**, and then click **Start**.
5.  Verify that the database migration has been successful by opening the WSUS administrative console (click **Start**, click **Administrative Tools**, and then click **Microsoft Windows Server Update Services 3.0)**.

| ![](images/Cc708558.note(WS.10).gif)Nota   |
|-------------------------------------------------------------------------|
| You might have to restart the server for these settings to take effect. |

#### Migrating the WSUS database from a Windows Internal Database instance to a SQL Server 2005 instance on a remote server

The goal of this scenario is to take the WSUS database (SUSDB) running in a Windows Internal Database instance on the WSUS server and move and upgrade it to a SQL Server 2005 instance running on a remote server. Only a full SQL Server 2005 database may be used in a remote SQL installation. Note that in each step, where appropriate, it is noted on which server you must perform the procedures.

#### Remote SQL scenario limitations

-   You cannot use a server configured as a domain controller for either the front end (FE) or the back end (BE) of the remote SQL pair.
-   You cannot use a server running as a Terminal Services server for the front end of the remote SQL pair.
-   You cannot use Windows Internal Database for database software on the back-end server.
-   Both the front-end and the back-end servers must be joined to an Active Directory domain.

#### Prerequisites

-   FE starting configuration:
    -   Windows Server 2003 Service Pack 1 or Windows Server 2008 operating system
    -   WSUS with Windows Internal Database
-   BE starting configuration:
    -   Windows Server 2003 Service Pack 1 or Windows Server 2008 operating system
    -   SQL Server 2005

#### Step 1 \[on FE\]: Install Microsoft SQL Server 2005 with "Client Tools Only" option.

This step will enable you to use the SQL Server Enterprise Manager on FE.

#### Step 2 \[on FE\]: Stop the IIS Admin service and the Update Services service.

-   Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Services**.
-   Right-click **IIS Admin Service**, and then click **Stop**.
-   Right-click **Update Services**, and then click **Stop**.

#### Step 4: Copy the SUSDB.mdf and SUSDB\_log.ldf files from FE to BE.

-   In Step 2, you noted the folder location on FE where these files are stored. Copy the files to this folder on BE.

#### Step 5 \[on BE\]: Attach the WSUS database to a SQL Server 2005 instance.

-   Attach **SUSDB** to the destination SQL instance.
-   Under the instance node, right-click **Databases**, select **Properties**, and then click **Attach**.
-   In the **Attach Databases** box, under **Databases to attach**, browse to the location of the susdb.mdf file (by default this is **C:\\WSUS\\UpdateServicesDbFiles** if you installed Windows Internal Database), and then click **OK**.

#### Step 6 \[on BE\]: Verify that the FE machine account has login permissions to the SQL Server instance and to the WSUS database.

-   Verify permissions on the SQL Server instance. In SQL Server Management Studio, open the instance and select **Security**, then **Logins**. The FE machine account should be listed as a login. If it is not, it should be added.
-   Verify permissions on the database. Right-click the database, select **Properties** and then click **Permissions**. The FE machine account should be listed as a login. If it is not, it should be added.
-   Verify members of the webService role. Under the WSUS database, select **Roles**, then right-click webService and select **Properties**. The FE machine account should be listed as a member of this role. If it is not, it should be added.

#### Step 7 \[on FE\]: Configure the FE computer to use the database on the BE computer.

In this step, you edit the registry to point WSUS to the destination SQL instance.

-   Click **Start**, click **Run**, type **regedit**, and then click **OK**.
-   Find the following key: **HKLM\\SOFTWARE\\Microsoft\\UpdateServices\\Server\\Setup\\SqlServerName**
-   In the **Value** data box, type **\[BEName\]\\\[InstanceName\]**, and then click **OK**. If the instance name is the default instance, then simply type **\[BEName\]**.

| ![](images/Cc708558.note(WS.10).gif)Nota |
|-----------------------------------------------------------------------|
| When typing \[BEName\], do not add the domain name before the name.   |

#### Step 8 \[on FE\]: Start the IIS Admin service and the Update Services service.

-   Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Services**.
-   Right-click **IIS Admin Service**, and then click **Start**.
-   Right-click **Update Services**, and then click **Start**.

#### Step 9: Verify that the database migration was successful.

Open the WSUS administrative console (click **Start**, click **Administrative Tools**, and then click **Microsoft Windows Server Update Services 3.0)**.

| ![](images/Cc708558.note(WS.10).gif)Nota    |
|--------------------------------------------------------------------------|
| You might need to restart FE in order for these settings to take effect. |

For more information about the databases you can use with WSUS, see the following:

-   In this guide, see [Managing the Databases](https://technet.microsoft.com/d99cdd74-fbf4-4706-b2a2-a58728beef22).
-   In [Deploying Microsoft Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=79983), see "Choose the Database Used for WSUS 3.0".
-   In [Deploying Microsoft Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=79983), see "Appendix B: Configure Remote SQL" for general information about setting up WSUS using a remote SQL Server 2005 server to host the WSUS database.
