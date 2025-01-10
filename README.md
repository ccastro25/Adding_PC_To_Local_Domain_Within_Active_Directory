# Adding_PC_To_Local_Domain_Within_Active_Directory
connecting pc to server


## Configuring the VM Network for Server
1. Select `Devices > Network`
2. Under Adapter 1:
    - Select `Bridge Adapter` at the `Attached to:` option
3. Click OK


https://github.com/user-attachments/assets/96b1fd1c-d504-40fd-b292-1352d0e09a2c


## Configuring IP for the Server
1. Go to `Start > Windows System > Control Panel`
2. Navigate to `Network and Internet > Network and Sharing Center`
3. Select `Change adapter settings` on the left
4. Right-click on the Ethernet icon
5. Select `Properties`
6. Double-click `Internet Protocol Version 4 (TCP/IPv4)`
7. In the new window for Internet Protocol:
    - Select `Use the following IP address`
    - Enter `168.16.1.2` for the IP address
    - Enter `255.225.0.0` for the subnet mask
    - Enter `168.16.1.1` for the Default Gateway
    - Select `Use the following DNS server address`
    - Enter `168.16.1.2` for `Preferred DNS server`
    - Enter `168.16.1.1` for `Alternate DNS server`
8. Press OK in the Protocol Version window
9. Press OK in the Ethernet Properties window





## Check IP through Command Prompt
1. Go to search
2. Type `cmd` and press Enter
3. Type `ipconfig` in the command prompt to see what you configured



https://github.com/user-attachments/assets/d0fe3d83-7867-42db-b2a3-f7e0826554c6


# Preparing Network for PC

## Configuring the VM Network for Server
1. Select `Devices > Network`
2. Under Adapter 1:
    - Select `Bridge Adapter` at the `Attached to:` option
3. Click OK

## Configuring IP for the PC
1. Go to `Start > Windows System > Control Panel`
2. Navigate to `Network and Internet > Network and Sharing Center`
3. Select `Change adapter settings` on the left
4. Right-click on the Ethernet icon
5. Select `Properties`
6. Double-click `Internet Protocol Version 4 (TCP/IPv4)`
7. In the new window for Internet Protocol:
    - Select `Use the following IP address`
    - Enter `168.16.1.3` for the IP address
    - Enter `255.225.0.0` for the subnet mask
    - Enter `168.16.1.1` for the Default Gateway
    - Select `Use the following DNS server address`
    - Enter `168.16.1.2` for `Preferred DNS server`
    - Enter `168.16.1.1` for `Alternate DNS server`
8. Press OK in the Protocol Version window
9. Press OK in the Ethernet Properties window

## Check IP through Command Prompt
1. Go to search
2. Type `cmd` and press Enter
3. Type `ipconfig` in the command prompt to see what you configured

# Creating New Rule for Firewall

1. Go to `Start > Windows System > Control Panel > System and Security`
2. Select `Windows Defender Firewall` on the left
3. Select `Advanced settings` on the left
4. In the new window:
    - Right-click `Inbound Rules` and select `New Rule`
    - In the Rule Type Step, select the `Custom` option and click `Next`
    - Click `Next` in the Program Step
    - Leave the default option in the Protocol and Ports options
    - Select `These IP addresses` under **Which local IP addresses does this rule apply to?**
    - Select `Add`
    - In the IP Address window:
        - Select `This IP address or subnet`
        - Enter `168.16.1.2` **This is the server's address**
        - Press OK
5. Press `Next`
6. In the `Action` Step:
    - Under **What action should be taken when a connection matches the specified conditions?**
        - Select `Allow the connection if it is secure`
7. Click `Next`
8. In the `Users`, `Profile`, and `Profile` Steps:
    - Leave the default and press `Next`
9. In the `Name` Step, give it a name

# Adding PC to Local Domain

1. Select `Start > Settings`
2. Followed by `System`
3. Scroll down to `About`
4. Once again scroll down and click `Rename this PC (Advanced)`
5. Under the `Computer Name` tab, click `Change`
6. At the Computer Name window, domain Changes
7. Select `Domain` under `Member of`
    - Enter `castro.local`
    - Press OK
8. At the Windows Security window:
    - Enter the username and password
    - Press OK
9. You should now see a window saying:
    - `Welcome to the castro.local domain`
10. Windows will now restart

# Confirming PC is in Local Domain

1. From Windows Server VM:
    - Within Server Manager Dashboard, select `Active Directory Domains and Trusts`
    - Select `castro.local > Computers`
    - The PC should be listed
2. From Windows PC VM:
    - Go to `Start > Settings > System > About`
    - The Domain name will be in the Full device name

