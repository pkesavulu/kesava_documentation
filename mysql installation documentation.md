# MySql documentation


> Follow the below step to install mysql

- To download mysql click here 
  [mysql](https://dev.mysql.com/downloads/)

- To choose the "MySQL Community Server" and click the download button. it is re-direct to here "https://dev.mysql.com/downloads/mysql/" 
- Next choose the operating system(like windows) and click the "Go to Download Page".
- There choose the first one like 
<Windows (x86, 32-bit), MSI Installer> it is 15.8 MB and click the download button the download will start.
- Once download process completes try to install the "mysql installer web community software".
- First step accept the licence Agreement and click the next button. 
- Next Choose the setup type is "Developer Defualt" and click the next button.
- Next to set the path for install Directory(C:\apps\mysql Server 8.0) & Data Directory(C:\apps\mysql Server 8.0\mysql data) then click the Execute button the installation process will start. Once the installation process completed then click Next button.
- Then "product configuration" tab will appear to click next button for configuration and choose the standalone MYSQL Server in Group        Replication and click the next button.
- Then choose the "configuration type" is Development computer and change the port number "6600" in Type and Networking tab and finally click the next button.
- Then choose the "Authentication Method" type is use Strong Password Encryption for Authentication in Authentication Method and finally click the next button.
- Then set the Root Account Password as "thalesadmin" and create new MySql user same as like below.

```
Username    : thales
Host        : localhost
Role        : DB Admin
Authentication:Mysql
Password    : thalesadmin
confirmation Password : thalesadmin

```
- Then set Windows service Name as "MySQL80" and click the Next button.
- Finally click the Execute button in "Apply configuration" tab and click the Finish button.
- Then "MySql Router Configuration" tab will appear to if it is require try to configure otherwise to click finish button.
- After "Connect To Server" tab will appear try set user as thales and password as thalesadmin to click the check button to check the connection succeeded or not and click the Next button.
- Then "Apply configuration" tab will appear try to click execute button and finally click the finish button.
- Finally to click the finish button in "installation complete" tab we are done the all installation process successfully. 




