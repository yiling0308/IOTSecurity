# The OWASP IoT Attack Surface Areas (DRAFT) are as follows:

>> ## Ecosystem Access Control (生態系統存取控制)
>- Implicit trust between components (組件之間的絕對信任)
>- Enrollment security (登記安全)
>- Decommissioning system (除役系統)
>- Lost access procedures (失去訪問程序)

>> ## Device Memory (記憶體設備)
>- Cleartext usernames (明文用戶名)
>- Cleartext passwords (明文密碼)
>- Third-party credentials (第三方憑證)
>- Encryption keys (加密密鑰)

>> ## Device Physical Interfaces (物理介面設備)
>- Firmware extraction (韌體拔出)
>- User CLI (使用者命令列)
>- Admin CLI (管理員命令列)
>- Privilege escalation (特權升級)
>- Reset to insecure state (重置為不安全狀態)
>- Removal of storage media (移除儲存裝置)

>> ## Device Web Interface (網路介面設備)
>- SQL injection (SQL注入式攻擊、SQL資料隱碼攻擊)
>- Cross-site scripting (跨網站指令碼)
>- Cross-site Request Forgery (跨網站的偽造要求)
>- Username enumeration (使用者名稱的獲取)
>- Weak passwords (脆弱的密碼)
>- Account lockout (帳戶鎖定)
>- Known default credentials (預設驗證機密性資料)

>> ## Device Firmware (韌體設備)
>- Hardcoded credentials (硬式編碼憑證)
>- Sensitive information disclosure (敏感資訊洩漏)
>- Sensitive URL disclosure (敏感性網址)
>- Encryption keys (加密密鑰)
>- Firmware version display and/or last update date (韌體版本顯示/最後更新日期)

>> ## Device Network Services (網路服務設備)
>- Information disclosure
>- User CLI
>- Administrative CLI
>- Injection
>- Denial of Service
>- Unencrypted Services
>- Poorly implemented encryption
>- Test/Development Services
>- Buffer Overflow
>- UPnP
>- Vulnerable UDP Services
>- DoS

>> ## Administrative Interface (管理介面)
>- SQL injection
>- Cross-site scripting
>- Cross-site Request Forgery
>- Username enumeration
>- Weak passwords
>- Account lockout
>- Known default credentials
>- Security/encryption options
>- Logging options
>- Two-factor authentication
>- Inability to wipe device

>> ## Local Data Storage (本地數據存儲)
>- Unencrypted data
>- Data encrypted with discovered keys
>- Lack of data integrity checks

>> ## Cloud Web Interface (網路雲端介面)
>- SQL injection
>- Cross-site scripting
>- Cross-site Request Forgery
>- Username enumeration
>- Weak passwords
>- Account lockout
>- Known default credentials
>- Transport encryption
>- Insecure password recovery mechanism
>- Two-factor authentication

>> ## hird-party Backend APIs (第三方後端APIs)
>- Unencrypted PII sent
>- Encrypted PII sent
>- Device information leaked
>- Location leaked

>> ## Update Mechanism (更新機制)	
>- Update sent without encryption
>- Updates not signed
>- Update location writable
>- Update verification
>- Malicious update
>- Missing update mechanism
>- No manual update mechanism

>> ## Mobile Application (行動應用程式)
>- Implicitly trusted by device or cloud
>- Username enumeration
>- Account lockout
>- Known default credentials
>- Weak passwords
>- Insecure data storage
>- Transport encryption
>- Insecure password recovery mechanism
>- Two-factor authentication

>> ## Vendor Backend APIs (供應商後端APIs)
>- Inherent trust of cloud or mobile application
>- Weak authentication
>- Weak access controls
>- Injection attacks

>> ## Ecosystem Communication (生態傳播)
>- Health checks
>- Heartbeats
>- Ecosystem commands
>- Deprovisioning
>- Pushing updates

>> ## Network Traffic (網路交通)
>- LAN
>- LAN to Internet
>- Short range
>- Non-standard
