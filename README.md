# NessusScan
Using Nessus to scan and search for vulnerabilities
For this I will be Using Tenable Nessus vulnerabilty scanner, my host machine to run the scan that will be directed to a Windows 10 Virtual Machine running on Oracle VM 

Create a VM with Windows 10 ISO, I decided to use Oracle Virtualbox as Hypervisor for my virtual machine, then check the VM IP (Going to Network settings) and make a ping from my host machine to the VM to ensure connection: going to windows "cmd" and then using the command "ping" with the IP of my VM, I add "-T" to the command so it will send pings until I stop it.

![0](https://github.com/user-attachments/assets/99fe80f2-4906-4389-ba1e-73f354dd6608)

![1](https://github.com/user-attachments/assets/1c45abe9-e206-4cba-8a74-9857bdedee1f)

I go to Nessus/new scan/ basic network scan to create a scan templates as shown in the image and then save that configuration and then run a scan

![3](https://github.com/user-attachments/assets/7f243096-aebb-4c7e-94b5-fd1c17384c20)

-Basic Scan: After the scan is complete I review the results as the image shows, most vulnerabilities being information type, 1 low level, and 1 mixed (Based in CVSS v3.0)

![4](https://github.com/user-attachments/assets/021c926d-ba45-48f2-9993-0e9c6ce48a06)


Credentials Scan: for a more thorough scan I need to give Nessus credentials for the Machines that will undergo a scan, but they will have to be properly set up to allow Nessus's deeper scan
Im going to proceed with some of Tenable recommendations for credential checks on Windows (documentation here https://docs.tenable.com/nessus/Content/CredentialedChecksOnWindows.htm#Configure-a-Local-Account)

To configure windows properly its necessary to disable UAC (User Account Control), open the Control Panel, select User Accounts, and set Turn User Account Control to Off.

First I go to Services and allow Remote Registry

Second I select Windows tab/Registry editor to add a key that will further allow the remote scan, from Reg edit the whole direction is as shown in image, and then I Add a new DWORD (32 bits) "LocalAccountTokenFilePolicy", enter inside the new DWORD an Set its value to 1

Now it is time for the new scan with credentials, but to add those credentials to Nessus first go to my scans and select the Machine to add the credentials, then settings/credentials/windows and select the authentication method, username and password (Tip: for be sure about the username I open a CMD window and input the command "whoami" and that will print the current username)
