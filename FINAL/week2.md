#### Web Attacks漏洞測試
Command Injection
![Command Injection](picture/commandinjection.png)
SQL Injection
![SQL Injection](picture/sqlinjection.png)<br>
![SQL Injection2](picture/sqlinjection2.png) <br>
File Inclusion
![File Inclusion](picture/fileinclusion.png)<br>
#### 檢視apache web server的log檔
cat access.log
![showpasswdlog](picture/showpasswd.png)<br>
#### 安裝modsecurity

    sudo apt-get update
    sudo apt-get install libapache2-modsecurity -y
  
![update](picture/update.png)<br>
![installlibapache](picture/installlibapache.png)<br>

    sudo  service apache2 reload
    sudo apachectl -M | grep --color security2
  
![install](picture/)<br>
檢視ModSecurity default rules
修改設定檔
  
  sudo vim /etc/apache2/mods-enabled/security2.conf    

#### Web RE-Attacks漏洞測試
  
