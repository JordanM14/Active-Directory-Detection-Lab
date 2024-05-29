# Active-Directory-Detection-Lab

## Objective

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The main goal was to analyze logs in Splunk and generate telemetry to mimic real-world attacks scenarios. This hands on experience has helped me Develope the understanding of SIEM tools like splunk, 

### Skills Learned

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Splunk (SIEM) system for log ingestion and analysis.
- Oracle VM VirtualBox 
- Telemetry generation tools to create realistic network traffic and attack scenarios.
- windows 10, kali linux, and ubuntu operating systems used to create realistic envirnment
- crowbar (Telemetry)
- atomic red team (Telemetry)

## Steps
### Diagram
![diagram](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/26175927-e4f3-4353-afe3-f073449fcd86)

### STEP 1: Download the following VMs

![machine downloads](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/5904d776-52c0-49a9-a770-cb574746376b)

- Windows 10(Victim)
- Kali-Linux(Attacker)
- Windows Server
- ubuntu(Splunk server)

### Step 2: Install and Configure Sysmon and Splunk

### -install splunk and create a user
![splunk download 1](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/9e10512b-4b0c-48fa-a126-1de2e388b8de)![splunk install4](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/473a96bc-68e2-4b03-a954-d7dede29f607)

### -install sysmon
- ![sysmon powershell download TM](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/c4524b72-d990-4874-beca-db17f7a640c5)

### -import pre-installed sysmon configurations 
![SPLUNK INPUTS FILE](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/4c751acf-44d9-42a6-873f-86c249300041)

### -install and configure splunk UF 
![splunk target machine UF2](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/b62c90ec-4084-4691-9480-7491771a6753)![splunk UF TM3](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/c3aba3e8-7a1a-47c5-a640-a061162d926c)



### -create index and enable splunk to receive data
![creating new splunk index](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/ce030dc5-cb01-4e87-ab5f-d9f43dad94ea)![enable splunk to reciev data](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/f7ef7503-d114-428c-8e3b-0853e84ac5f5)

### -repeat steps on windows server

### Step 3: Configure Windows Server And Active Directory

### -install active directory domain services
![ACTIVE DIRECTORY DOWNLOAD](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/6e380208-b1a2-4390-9379-39757f96d7d4)

### -promote server to domain controller 
![PREMOTE SERVER TO DC](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/c7e4d29e-f9d1-4173-8a8a-ffc4d5b8db4f)

### -create new organizational unit with users
![new organtinal groups](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/3f7cbee7-eacd-4fe3-9701-6089dd49aeb6)

### -add target pc to domain
![add target pc to domain](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/c557b8dd-34e8-449a-8682-83e6fb01ba0b)

### Step 4: perform brute force attack and view telemetry in splunk

### -save the top 20 passwords from rockyou.txt to password.txt and add the correct passwords
- rockyou.txt is a preinstalled list with over 100 passwords on linux
![getting top 20 passwords pt2](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/fb651548-5c0c-4bf8-8324-c4838b66f2ef)![addig password to list pt 2](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/f569225e-19ad-4267-8823-a3ee41357c6b)

### -execute bruteforce against user Tsmith with crowbar
![execute bruteforce](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/2be10473-76fd-4a24-b4c2-59d33d3357dd)

### -view telemetry in splunk
![brute force in splunk](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/e333a13f-7094-49e1-82c0-e6b5b58d788e)![brute force in splunk pt 2](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/fbeca0fb-b2c2-44f9-a1d4-2d2cb681e211)

###  Step 4: perform MITRE ATT&CK T1059.001 using ART and view telemetry in splunk
![MITRE ATT CK T1059 001](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/ba440c3e-4fbd-4395-9917-dce1746a7403)

### -perfrom attack using ART, the attack creates a new user 
![art](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/0b07862a-569d-45fc-93e6-02ff649d27e0)

### -view telemetry in splunk
![new local user](https://github.com/JordanM14/Active-Directory-Detection-Lab/assets/90062863/2f0c418d-d2ab-4d09-94fe-1d5d439fc90e)












