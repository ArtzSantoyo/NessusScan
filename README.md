# Nessus Scan
Using Nessus to scan and search for vulnerabilities
For this I will be Using Tenable Nessus vulnerabilty scanner, my host machine to run the scan that will be directed to a Windows 10 Virtual Machine running on Oracle VM 

Create a VM with Windows 10 ISO, I decided to use Oracle Virtualbox as Hypervisor for my virtual machine, then check the VM IP (Going to Network settings) and make a ping from my host machine to the VM to ensure connection: going to windows "cmd" and then using the command "ping" with the IP of my VM, I add "-T" to the command so it will send pings until I stop it.

![0](https://github.com/user-attachments/assets/99fe80f2-4906-4389-ba1e-73f354dd6608)

![1](https://github.com/user-attachments/assets/1c45abe9-e206-4cba-8a74-9857bdedee1f)

I go to Nessus/new scan/ basic network scan to create a scan templates as shown in the image and then save that configuration and then run a scan

![3](https://github.com/user-attachments/assets/7f243096-aebb-4c7e-94b5-fd1c17384c20)

-Basic Scan: After the scan is complete I review the results as the image shows, most vulnerabilities being information type, 1 low level, and 1 mixed (Based in CVSS v3.0)

![4](https://github.com/user-attachments/assets/021c926d-ba45-48f2-9993-0e9c6ce48a06)


Finally after the scan is completed, its possible to generate a report

![report](https://github.com/user-attachments/assets/50f55d6a-ccbc-4312-83f3-b6905aed0b61)

And select to prefered template to receive the report info, according to the user or company needs

![report 1](https://github.com/user-attachments/assets/e31c03aa-ef56-4f52-a94b-5116668bfc05)
