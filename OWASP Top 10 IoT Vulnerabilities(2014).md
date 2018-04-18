# I1:Insecure Web Interface
- Scenario #1: The web interface presents "Forgot Password" functionality which upon entering an invalid account informs the attacker that the account does not exist. Once valid accounts are identified, password guessing can begin for an indefinite amount of time if no account lockout controls exist.

      Account john@doe.com does not exist.

- Scenario #2: Web interface is susceptible to cross-site scripting.

      http://xyz.com/index.php?user=<script>alert(123)</script> ... Response from browser is an alert popup.

In the cases above, the attacker is able to easily determine if an account is valid or not and is also able to determine that the site is susceptible to cross-site scripting (XSS).
# I2:Insufficient Authentication/Authorization
- Scenario #1: The interface only requires simple passwords.

      Username = Bob; Password = 1234

- Scenario #2: Username and password are poorly protected when transmitted over the network.

      Authorization: Basic YWRtaW46MTIzNA==

In the cases above, the attacker is able to either easily guess the password or is able to capture the credentials as they cross the network and decode it since the credentials are only protected using Base64 Encoding.
# I3:Insecure Network Services
- Scenario #1: Fuzzing attack causes network service and device to crash.

      GET %s%s%s%s%s%s%s%s%s%s%s%s%s%s%s HTTP/1.0

- Scenario #2: Ports open to the internet possibly without the user's knowledge via UPnP.

      Port 80 and 443 exposed to the internet via a home router.

In the cases above, the attacker is able to disable the device completely with an HTTP GET or access the device via the internet over port 80 and/or port 443.
# I4:Lack of Transport Encryption/Integrity Verification
- Scenario #1: The cloud interface uses only HTTP.

      http://www.xyzcloudsite.com

- Scenario #2: Username and password are transmitted in the clear over the network.

      http://www.xyzcloud.com/login.php?userid=3&password=1234

In the cases above, the attacker has the ability to view sensitive data in the clear due to lack of transport encryption.
# I5:Privacy Concerns
- Scenario #1: Collection of personal data.

      Date of birth, home address, phone number, etc.

- Scenario #2: Collection of financial and/or health information.

      Credit card data and bank account information.

In the cases above, exposure of any of the data examples could lead to identity theft or compromise of accounts.
# I6:Insecure Cloud Interface
- Scenario #1: Password reset indicates whether account is valid.

      Password Reset "That account does not exist."

- Scenario #2: Username and password are poorly protected when transmitted over the network.

      Authorization: Basic S2ZjSDFzYkF4ZzoxMjM0NTY3

In the cases above, the attacker is able to either determine a valid user account or is able to capture the credentials as they cross the network and decode them since the credentials are only protected using Base64 Encoding.
# I7:Insecure Mobile Interface
- Scenario #1: Password reset indicates whether account exist or not.

      Password Reset "That account does not exist."

- Scenario #2: Username and password are poorly protected when transmitted over the network.

      Authorization: Basic S2ZjSDFzYkF4ZzoxMjM0NTY3

In the cases above, the attacker is able to either determine a valid user account or is able to capture the credentials as they cross the network and decode them since the credentials are only protected using Base64 Encoding.
# I8:Insufficient Security Configurability
- Scenario #1: No ability to enforce strong password policies.

      Admins and users are allowed to create passwords for their accounts.

- Scenario #2: No ability to enable encryption of data at rest.

      Password or other sensitive data stored on the device may not be encrypted.

In the cases above, the attacker is able to use the lack of these controls to get access to user accounts with weak passwords or access data at rest which has protection.
# I9:Insecure Software/Firmware
- Scenario #1: Update file is transmitted via HTTP.

      http://www.xyz.com/update.bin

- Scenario #2: Update file is unencrypted and human readable data can be viewed.

      �v�ñ]��Ü��Qw�û]��ˇ3DP�Ö�∂]��ˇ3DPadmin.htmadvanced.htmalarms.htm

In the cases above, the attacker is able to either capture the update file or capture the file and view it's contents.
# I10:Poor Physical Security
- Scenario #1: The device can be easily disassembled and storage medium is an unencrypted SD card.

      SD card can be removed and inserted into a card reader to be modified or copied.

- Scenario #2: USB ports are present on the device.

      Custom software could be written to take advantage of features such as updating via the USB port to modify the original device software.

In both cases, an attacker is able to access the original device software and make modifications or simply copy specific target data.
