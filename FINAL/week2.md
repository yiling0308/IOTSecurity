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
  
![install2](picture/install2.png)<br>

    sudo mv /etc/modsecurity/modsecurity.conf-recommended /etc/modsecurity/modsecurity.conf
    
![mv](picture/mv.png)<br>

    sudo sed -i "s/SecRuleEngine DetectionOnly/SecRuleEngine On/" /etc/modsecurity/modsecurity.conf
    sudo sed -i "s/SecResponseBodyAccess On/SecResponseBodyAccess Off/" /etc/modsecurity/modsecurity.conf
    
![sed](picture/sed.png)<br>

    sudo vim /etc/apache2/mods-enabled/security2.conf

![sed](picture/vimsecurity.png)<br>

    sudo service apache2 reload
    sudo cp /usr/share/modsecurity-crs/base_rules/modsecurity_crs_41_sql_injection_attacks.conf /usr/share/modsecurity-crs/activated_rules/
    
![cp](picture/cp.png)<br>

#### Web RE-Attacks漏洞測試
!['or'1'=='1'](picture/injc.PNG)<br>
![inc](picture/injc.PNG)<br>
