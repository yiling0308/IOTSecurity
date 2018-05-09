# The OWASP IoT Attack Surface Areas (DRAFT) are as follows:

>> ## Ecosystem Access Control (生態系統存取控制)
>- Implicit trust between components
>- Enrollment security
>- Decommissioning system
>- Lost access procedures

>> ## Device Memory (記憶體設備)
>- Cleartext usernames
>- Cleartext passwords
>- Third-party credentials
>- Encryption keys

>> ## Device Physical Interfaces (物理介面設備)
>- Firmware extraction
>- User CLI
>- Admin CLI
>- Privilege escalation
>- Reset to insecure state
>- Removal of storage media

>> ## Device Web Interface (網路介面設備)
>- SQL injection
>- Cross-site scripting
>- Cross-site Request Forgery
>- Username enumeration
>- Weak passwords
>- Account lockout
>- Known default credentials

>> ## Device Firmware (韌體設備)
>- Hardcoded credentials
>- Sensitive information disclosure
>- Sensitive URL disclosure
>- Encryption keys
>- Firmware version display and/or last update date

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
