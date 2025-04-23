# Team structure

- Linux
  - Server Maintenance
  - Recovery
  - Infrastructure planning and expansion
- Windows (AD,o365)
  - Server Maintenance
  - Recovery
  - Infrastructure planning and expansion
  - Software installation
  - Mailbox management
  - AD Permissions
- Hardware
  - Laptop installation for new joiners!
  - Testbench installation
  - Laptop and testbench maintenance
  - Other/Optional hardware handling(door locks, projectors etc.)
- Networking
  - Network maintenance and expansion
  - Firewall management
  - VPN management 
- Virtualization
  - Hypervisor maintenance
  - Storage maintenance 
  - etc
- Security
  - Spam/Phishing email review and remediation
  - ESET, Wazuh, Graylog event review and remediation
---
# Day 1

## What did we learn?!

- How check a computer is online
  1. ping ip adress 
- How many users we have in Windows and wich permission they have
  1. type users in search, then check haw many we have and wich permissions
- How update a server 
  1. We have to take a snapshot, sign in in a server type our name, then we start the update process

---

## Homework

- How to check if a port is open on a remote machine?
- How to check if certain software is installed and uninstall/re-install in windows?
- How to check running processes in windows and terminate/kill them if not needed?
- How to login remotely to a windows machine?
- How to update windows?
- How to change IP address in windows?+

---
## Completing the Homework;
1.  How to update windows?
- Go to Settings, then go to Windows update, check windows update; 
- With using PowerShell check for update command: `Get-WindowsUpdate`;For installing: `Install-Windows Update`;

2.  How to check if certain software is installed and uninstall/re-install in windows?
- Go to settings, then go to apps -> installed apps; Here we can check our installed apps, uninstal, or re-instal;

3. How to check running processes in windows and terminate/kill them if not needed?
- Press `Ctrl+Shift+Esc` or `Ctrl+Alt+Del` -> select task manager; then we see the tab processes, here we can check current processes, and we can terminate/kill them, or change priority;

3. How to login remotely to a windows machine?
 - On current Pc in the search box on the taskbar, type Remote Desktop, then select Remote Desktop Connection and type name of your PC, IP adress; To find out the ip address, we need go to CMD, and type command: `ipconfig`;
 
4.  How to check if a port is open on a remote machine?
 - We have to open CMD, then type the following command: telnet [remote_ip] [port]; if the port is open, we can see black screen or a response from from the service;  
 If the port is close, we can see a connection error message:
 Also we can use PowerShell, and use this command: Test-Net Connection -ComputerName [remote_ip] Port [Port]
5. How to change IP address in windows?
 - Control panel -> Network and sharing center -> adapter settings->our conection, IPv4 properties;
 - Or we can use CMD, type following command:`ipconfig /release`; after this type the following command to get a new IP: `ipconfig /renew`; then we can check our new IP following command: `ipconfig`;
 Also we can use a VPN for changing IP; Install the VPN software and then launch the VPN and connect to a server in the Desired location. 
 Our publick ip address will change to the assigned by the VPN server.

 --- 

# Day 2 
## Homework 
1. How to navigate and manage files in cmd? 
2. How to allow firewall port in windows?
3. How to manage bitlocker? 
4. How to prepair of bootable usb-stick? windows and linux;
5. How to manage local users permisiion in Windows? 

--- 

# Completing the Homework
1. How to navigate and manage files in cmd? 
- `cd` road to folder; `dir` go to folder; cd .. go outside; `mkdir` create a new folder;
rmdir; remove folder; create a new empty file type `nul > name_of_file.txt` for delit `del name_of_file.txt`; copy and paste copy file.txt C:\ test\;

2. How to manage bitlocker?
-  Go to search box on taskbar, then type Bitlocker; In this window we can suspend protection, change how drive is unlocked at start-up, back up your recovery key, change current PIN and turn off bitlocker; 
3. How to prepair of bootable usb-stick? windows and linux;
- `Windows` We go on the official microsoft website and download `MediaCreationTool`, then we run MediaCreationTool, and insert usb-stick in computer, and follow the instructions; After that we have bootable usb-stick;
- `Linux` 1 step we need download a linux, on our Pc, then with `Rufus` or `Ventoy` we can create bootable usb-stick; For example with Rufus, select boot selection, select iso, choose partition scheme, GPT more preferable for new PC, file system `FAT32`, then push start
4. How to manage local users permision in Windows? 
- windows+x computer managment, local users and groups -> users select the desired user, for example labor -> member of, and here we can add this user in different groups. for example add `labor` in group guests; 
5. How to allow firewall port in windows?
- win+r system and security -> windows firewall, advanced setting -> inbound rules, new rules, then port -> next, choose protocol TCP or UDP -> Next and then select a port wich you needed, for example 8080, then mark profiles, domain, private, or publick -> type new name of port 8080;



---
# Day 3

# Homework 
1. Basics markdown
2. Generate and use ssh keys;
3. Flush windows dns;
 Write script that exports windows event logs to text; Script bat and powershell;
4. Scan all ports of remote machine;
5. Transfer files from one linux machine to another, the same on windows;
7. Write script that exports windows event logs to text; Script bat and powershell;
8. Create a local git repository and push it up stream;
9. How to log to log in to remote linux machine?

---

# Compliting the Homework

1. Basics markdown;
`#, ---, -, ``, _test_(italica),  **test**; 

```block for code
  ```

2. How to log to log in to remote linux machine?
- CMD: `ssh Tech1349-PC@10.24.14.11`; if we use not standart port, we have to type: `ssh -p40` if we use private key, we have to type `-i ~/.ssh/my_private_key.pem`;

3. Write script that exports windows event logs to text; Script bat and powershell;

- PowerShell: Create a new folder: `New-Item -ItemType Directory -Path "C:\Logs"` 

- Standart Windows logs For example with System: `Get-EventLog -LogName System | Out-File "C:\Logs\system_events.txt"`

- `Get-eventlog -logname application |Out-file "C:\logs\system_events.txt"`

- for bat `mkdir"C:\Logs"` and `wevtutil qe System /f:text > "C:\Logs\system_events.txt"`

4. Scan all ports of remote machine;
- first step for ubuntu/Debian: instaling nmap: sudo apt install nmap;
- nmap -p- 10.24.14.11;

- 
5. Transfer files from one Windows machine to another;
- Easiest method with usb stick or file sharing; for example google drive, or OneDrive, but it works just for not big files;

- The most usable method it Via shared folders (network); 

- control panel, than network and internet -> sharing center -> change advanced sharing settings; i have to turn on network discovery, and file and printer sharing; 
- choose the folder, wich you need; sharing tab; advanced sharing -> share this folder;



6. Create a local git repository and push it up stream; 

- mkdir my-project; cd-my-project; git init; git add . git commit -m.
- Create remote repository (upstream)
Github, create new repository; add remote repository : git remote add origin `link with our repository`
- If the main branch is called `main`: `git push -u origin main`;
- If the main branch is called `master`:
 `git push -u origin master`
 - git init - create local git-repository;
 - git remote add origin - add link of remote repository (upstream);
 - git push - downloads code and establishes links between branches;
7. Flush windows dns;
- Flush dns means clear windows dns cash; when you visit web-site, windows remembers ip adress; for examle google.com he tranlate like 142.250.190.78. but somtimes this ip adress getting old; and then web-site can 
may not open or open with an error;
-  CMD: `ipconfig /flushdns` 
8. Generate and use SSH keys;
- SSH-Secure Shell; 
- command for generation: `ssh-keygen -t-rsa`; show generated key(privat) `type %USERPROFILE%\.ssh\id_rsa` public `type %USERPROFILE%\.ssh\id_rsa.pub`




## Notes

Vlan14 a.k.a IT vlan (CIDR 10.21.14.0/24 [10.21.14.0 - 10.21.14.255])

Vlan114 also IT vlan (CIDR 10.21.114.0/24 [10.21.114.0 - 10.21.114.255])

## Day 4


Homework 
---
1. OCI layers explanation and examples 
- OCI (Open Container Initiative)
