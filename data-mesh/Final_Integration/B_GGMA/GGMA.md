# <a name="_toc85786504"></a>**Architecture for Data Integration – Data Mesh:**
![Diagram

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.001.png)

**Demo Environment**

**Startup**

Initial Setup

Putty

sudo su – oracle

OGG\_HOME:

![Text

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.002.png)

sudo systemctl status OracleGoldenGate


Oracle Source:

system/dmInteg\_1111#

[4:41](https://sales-tech-div.slack.com/archives/D013R4XLLMU/p1652910089939649)

C##GGADMIN/dmIntAdmin111#

**Task 1:**

In case you need to restart the database after reboot:

- lsnrctl start
- sqlplus / as sysdba
- startup
- show pdbs
- alter pluggable database all open;
- show pdbs
- SQL> show pdbs;

- `    `CON\_ID CON\_NAME                       OPEN MODE  RESTRICTED
- ---------- ------------------------------ ---------- ----------
- `         `2 PDB$SEED                       READ ONLY  NO
- `         `3 DMPDB11                        READ WRITE NO
- `         `4 DMPDB12                        READ WRITE NO
- `         `5 DMPDB13                        READ WRITE NO
- `         `6 DMPDB14                        READ WRITE NO

sqlplus /nolog

SQL> connect / as SYSDBA

SELECT username, account\_status FROM dba\_users WHERE ACCOUNT\_STATUS LIKE '%EXPIRED%';


select username, expiry\_date, account\_status from dba\_users where username like 'CDB%';

ALTER USER system ACCOUNT UNLOCK;

ALTER USER CDB$ROOT ACCOUNT UNLOCK;

C##GGADMIN

ALTER USER C##GGADMIN ACCOUNT UNLOCK;

ALTER USER ‘C##GGADMIN@DMDCB1’ ACCOUNT UNLOCK;

ALTER PROFILE DEFAULT LIMIT PASSWORD\_LIFE\_TIME UNLIMITED;



## <a name="_toc85786498"></a>VNC:
**Task 2:**

Pre-Installed on dmintegration

IP (Public)

129\.146.107.176 - dmintegration

132\.226.123.94- ggsaintegrate

Port: 5901

Password: welcome1

PUTTY TUNNEL SETUP for VNC:

![Graphical user interface, application

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.003.png)

## <a name="_toc85786501"></a>**GGMA:**

**Installed on the** 129.146.107.176 **instance in /u04 directory**

**Task 3:**

GGMA Console:

<http://129.146.107.176:7805>

Username: oggadmin

PWD: welcome1

GGHOME: /u04/ggma21c/ogg\_ma/

### **Administration Server:**

Credentialstore cdb: C##GGADMIN@DMDCB1

Pwd: welcome1

sqlplus C##GGADMIN/welcome1@dmintegration:1521/dmpdb12

### <a name="_toc85786502"></a>**Distribution Server:**

DB Name: dmpdb12

Extract Name:
### <a name="_toc85786503"></a>Capture:
GGBD within GGSA

Target: kafka in GGSA



# <a name="_toc85786505"></a>**Configuration Data Sources:**
## <a name="_toc85786506"></a>Lab 1: DB Load Preparation:
Task 1
### <a name="_toc85786507"></a>DB Parameters:
sqlplus C##GGADMIN/welcome1@dmintegration:1521/dmdcb1

ALTER SYSTEM SET ENABLE\_GOLDENGATE\_REPLICATION=TRUE;

SQL> alter database archivelog;

Database altered.

Task 2

SQL> alter database open;

Database altered.

SQL> ALTER DATABASE ADD SUPPLEMENTAL LOG DATA;

Database altered.

SQL> ALTER SYSTEM SWITCH LOGFILE;

System altered.

SQL> SELECT force\_logging, supplemental\_log\_data\_min FROM v$database;

FORCE\_LOGGING                           SUPPLEME

\--------------------------------------- --------

NO                                      YES

sqlplus / as sysdba

SQL> alter pluggable database all open read write;

Pluggable database altered.

sqlplus system/dmAppDev\_01111#@dmintegration:1521/dmpdb12

SQL> grant dba to osadata;

Grant succeeded.

SQL> select \* from user\_sys\_privs;


## **Configuration GG Microservices**

**Task 1:**

Login

<http://129.146.107.176:7806/?root=account>

![Graphical user interface, text, application, chat or text message

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.004.png)

**Task 2:**

Create Credentials

![](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.005.png)![](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.006.png)![Graphical user interface, text

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.007.png)

Configuration

Review credentials


Review Checkpoint![Table

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.008.png)

**Next:**

**Task 3:**

Create Extract


![](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.009.png)![Graphical user interface, text, application

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.010.png)

![Graphical user interface, text, application, email

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.011.png)

![Graphical user interface, application

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.012.png)

**Page Down**

![Graphical user interface, text, application

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.013.png)

Next

Paste parameter file

EXTRACT EXTLOG

USERIDALIAS ggadmin\_cdb DOMAIN OracleGoldenGate

EXTTRAIL /u04/ggma21c/ogg\_deploy/var/lib/data/lg

SOURCECATALOG dmpdb12

TABLE DATAINT.TRUCK\_STREAM;


![Graphical user interface, text, application, email

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.014.png)

**Create and Run**

### <a name="_toc85786513"></a>*Admin Server Credentials:*

- update schema for integration source

Next
###
<a name="_toc85786515"></a>**Task 4:**
### **GGMA Admin Client:**

[oracle@ dmintegration/ bin]$ ./adminclient

OGG (not connected) 1> connect http:// dmintegration::7805 as oggadmin password welcome1

Using default deployment 'deployment1'

OGG (http:// dmintegration::7805 deployment1 as ggsa\_sourcedb@DMDCB1/DMPDB12) 9> dblogin useridalias ggadmin\_cdb

Successfully logged into database CDB$ROOT.

OGG (http:// dmintegration:7805 deployment1 as ggadmin\_cdb@DMDCB1/CDB$ROOT) 12> REGISTER EXTRACT EXT1 DATABASE CONTAINER (DMPDB12)

2021-09-27T20:00:16Z  INFO    OGG-02003  Extract group EXT1 successfully registered with database at SCN 4209000.
##

## <a name="_toc85786516"></a>GoldenGate Microservices CDC in GGMA
**Task 5:**

Service Manager

![Graphical user interface, text, application, email

Description automatically generated](Aspose.Words.030976c5-b868-45b4-bb64-5c4ae1319aa9.015.png)







