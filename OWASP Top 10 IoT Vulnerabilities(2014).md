# I1:Insecure Web Interface (不安全的網頁介面)
- Scenario #1: The web interface presents "Forgot Password" functionality which upon entering an invalid account informs the attacker that the account does not exist. Once valid accounts are identified, password guessing can begin for an indefinite amount of time if no account lockout controls exist.     </br>
情境 #1 介面設計沒考慮到安全，例如攻擊者輸入正確帳號但密碼錯誤時，會告知密碼錯誤，而兩者同時錯誤會告知帳號與密碼錯誤，致使攻擊者知道使用者帳號

      Account john@doe.com does not exist.

- Scenario #2: Web interface is susceptible to cross-site scripting.     </br>
情境 #2 可能會造成反射式XSS或CSRF攻擊

      http://xyz.com/index.php?user=<script>alert(123)</script> ... Response from browser is an alert popup.

In the cases above, the attacker is able to easily determine if an account is valid or not and is also able to determine that the site is susceptible to cross-site scripting (XSS).     </br>
在上述情況下，攻擊者能夠輕鬆確定帳戶是否有效，並且還能夠確定該網站易受跨站點腳本（XSS）的影響
# I2:Insufficient Authentication/Authorization (不充分的認證與授權)
- Scenario #1: The interface only requires simple passwords.     </br>
情境 #1 重要裝置未設定密碼保護，或是使用”1234”等非常脆弱的密碼


      Username = Bob; Password = 1234

- Scenario #2: Username and password are poorly protected when transmitted over the network.     </br>
情境 #2 密碼在網路中以未經加密的方式傳輸，因而很容易被竊取


      Authorization: Basic YWRtaW46MTIzNA==

In the cases above, the attacker is able to either easily guess the password or is able to capture the credentials as they cross the network and decode it since the credentials are only protected using Base64 Encoding.     </br>
在上述情況下，攻擊者能夠輕鬆猜出密碼，或者能夠在憑證跨越網絡並對其進行解碼時捕獲憑證，因為憑證僅受Base64編碼保護。
# I3:Insecure Network Services (不安全的網路服務)
- Scenario #1: Fuzzing attack causes network service and device to crash.     </br>
情境 #1 因為網路服務並未針對所有的情況做檢查，而讓攻擊者使用Fuzzing Attack工具產生一堆隨機的亂數要求，因而造成系統當機或是被發現漏洞。

      GET %s%s%s%s%s%s%s%s%s%s%s%s%s%s%s HTTP/1.0

- Scenario #2: Ports open to the internet possibly without the user's knowledge via UPnP.     </br>
情境 #2 沒有做好防火牆的設置，以便讓攻擊者可以找到某區域的裝置存取方式，而在未經授權的情況下對裝置進行存取


      Port 80 and 443 exposed to the internet via a home router.

In the cases above, the attacker is able to disable the device completely with an HTTP GET or access the device via the internet over port 80 and/or port 443.     </br>
在上述情況下，攻擊者可以通過HTTP GET完全禁用設備或通過端口80和/或端口443通過互聯網訪問設備。
# I4:Lack of Transport Encryption/Integrity Verification (欠缺傳輸時的加密保護)
- Scenario #1: The cloud interface uses only HTTP.     </br>
情境 #1 未使用安全連線的方式進行資料傳輸

      http://www.xyzcloudsite.com

- Scenario #2: Username and password are transmitted in the clear over the network.     </br>
情境 #2 資料傳輸的過程中未加密

      http://www.xyzcloud.com/login.php?userid=3&password=1234

In the cases above, the attacker has the ability to view sensitive data in the clear due to lack of transport encryption.     </br>
# I5:Privacy Concerns (隱私威脅)
- Scenario #1: Collection of personal data.     </br>
情境 #1 直接收集與使用使用者個資的誤用案例

      Date of birth, home address, phone number, etc.

- Scenario #2: Collection of financial and/or health information.     </br>
情境 #2 間接侵害隱私範例

      Credit card data and bank account information.

In the cases above, exposure of any of the data examples could lead to identity theft or compromise of accounts.     </br>
在上述情況下，任何數據示例的暴露都可能導致身份盜用或帳戶損害。
# I6:Insecure Cloud Interface (不安全的雲端介面)
- Scenario #1: Password reset indicates whether account is valid.     </br>
情境 #1 可透過嘗試登入或密碼重設等動作，得知某使用者或裝置帳號是否存在


      Password Reset "That account does not exist."

- Scenario #2: Username and password are poorly protected when transmitted over the network.     </br>
情境 #2 在傳輸帳號與密碼資訊時未妥善保護以至於機密外洩


      Authorization: Basic S2ZjSDFzYkF4ZzoxMjM0NTY3

In the cases above, the attacker is able to either determine a valid user account or is able to capture the credentials as they cross the network and decode them since the credentials are only protected using Base64 Encoding.     </br>
在上述情況中，攻擊者能夠確定一個有效的用戶帳戶，或者能夠在他們通過網絡並對其進行解碼時捕獲憑證，因為憑證只使用Base64編碼進行保護。
# I7:Insecure Mobile Interface (不安全的行動介面)
- Scenario #1: Password reset indicates whether account exist or not.     </br>
情境 #1 善意的應用程式本身因為具有弱點，像是沒有密碼鎖等功能，以至於攻擊者取得手機後，可以操作行動裝置而進行攻擊

      Password Reset "That account does not exist."

- Scenario #2: Username and password are poorly protected when transmitted over the network.     </br>
情境 #2 使用者沒有使用密碼保護功能，以致於手機可以很容易的被竊取而使用

      Authorization: Basic S2ZjSDFzYkF4ZzoxMjM0NTY3

In the cases above, the attacker is able to either determine a valid user account or is able to capture the credentials as they cross the network and decode them since the credentials are only protected using Base64 Encoding.     </br>
在上述情況中，攻擊者能夠確定一個有效的用戶帳戶，或者能夠在他們通過網絡並對其進行解碼時捕獲憑證，因為憑證只使用Base64編碼進行保護。
# I8:Insufficient Security Configurability (不充分的安全設定)
- Scenario #1: No ability to enforce strong password policies.     </br>
情境 #1 無法強制要求使用強密碼

      Admins and users are allowed to create passwords for their accounts.

- Scenario #2: No ability to enable encryption of data at rest.     </br>
情境 #2 無法強制要求密碼加密

      Password or other sensitive data stored on the device may not be encrypted.

In the cases above, the attacker is able to use the lack of these controls to get access to user accounts with weak passwords or access data at rest which has protection.     </br>
在上述情況中，攻擊者能夠使用缺少這些控件來訪問具有弱密碼的用戶帳戶或訪問具有保護的靜止數據。
# I9:Insecure Software/Firmware (不安全的軟體與韌體)
- Scenario #1: Update file is transmitted via HTTP.     </br>
情境 #1 可以直接透過上傳檔案的方式上傳更新檔進行更新

      http://www.xyz.com/update.bin

- Scenario #2: Update file is unencrypted and human readable data can be viewed.     </br>
情境 #2 更新文件未加密，可以查看人類可讀的數據。

      �v�ñ]��Ü��Qw�û]��ˇ3DP�Ö�∂]��ˇ3DPadmin.htmadvanced.htmalarms.htm

In the cases above, the attacker is able to either capture the update file or capture the file and view it's contents.     </br>
在上述情況下，攻擊者能夠捕獲更新文件或捕獲文件並查看其內容。
# I10:Poor Physical Security (實體安全考量不足)
- Scenario #1: The device can be easily disassembled and storage medium is an unencrypted SD card.     </br>
情境 #1 重要資料存在如SD卡等可移除硬體上，因而被直接竊取

      SD card can be removed and inserted into a card reader to be modified or copied.

- Scenario #2: USB ports are present on the device.     </br>
情境 #2 可透過USB等外接介面連接裝置而進行資料竊取或竄改

      Custom software could be written to take advantage of features such as updating via the USB port to modify the original device software.

In both cases, an attacker is able to access the original device software and make modifications or simply copy specific target data.     </br>
在這兩種情況下，攻擊者都可以訪問原始設備軟件並進行修改或簡單地複制特定目標數據。
