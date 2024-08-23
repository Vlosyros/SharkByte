<p align="center">
  <img src="https://github.com/user-attachments/assets/9510e919-84f0-471b-998b-47c7b8d199ff" width="350" alt="SharkByte Logo">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Release_Date-April_2024-Blue?color=blue"> <img src="https://img.shields.io/badge/Contributors-Christos_Kappos_%26_Willow_Ersil-Green?    labelColor=grey&color=green"> <img src="https://img.shields.io/badge/Purpose-Let's_Scrap_Phishing-Blue?color=blue">
</p>

<h1 align="center">SharkByte: Human Error's Worst Nightmare</h1>
<p align="center">
  An all-in-one service designed to test whether there are controls to mitigate and combat a phishing attack.
</p>

## What is Phishing?
Phishing relies on human error, exploiting our curiosity, and taking advantage of users who let their guard down with minimal effort. Instead of utilizing sophisticated tools throughout the kill chain, phishing can be used to gain access to a victim's system through simple social engineering tactics. 

This often includes tactics such as persuading an individual to open a link, leading to a malicious website, or persuading an individual to download and open a program. 

![image](https://github.com/user-attachments/assets/d7ac49de-43e2-4923-aeaf-ad8dbd7da5a5)

Phishing is relatively easy to execute, so both amateur and experienced cybercriminals rely on this technique. 

## The Proliferation of Phishing:
The ever-growing increase in successful organizational compromise using phishing techniques has significantly increased. In 2024, there were various successful phishing cases, with some of the more critical cases including:

1. **<img src="https://img.shields.io/badge/AZURE-blue?logoColor=Orange&color=blue"> Data Breach (Phishing)** - In February 2024, Microsoft suffered from the largest data breach recorded. The success of this attack stemmed from phishing. Threat actors embedded malicious documents into emails that led victims to phishing websites. This attack targeted mid and senior-level company executives...
   
2. **<img src="https://img.shields.io/badge/MGM_Resorts-orange?logoColor=Orange&color=orange"> Data Breach (Vishing)** -  In September 2023, a well-respected hotel and casino chain, suffered a Vishing attack launched by APT ALPHV and Scattered Spider. The success of this attack stemmed from a Vishing attack, in which the attacker called MGM IT Help Desk requesting assistance with an account. Credentials were provided, which led to the attacks gaining administrator privileges to MGM’s Azure and Okta tenant environments...

With phishing being centered around human error, it is evident that something must be done to help decrease the success rate of phishing. 

## Getting to know the SharkByte Phishing Assessment Program:
Despite organizations’ ongoing efforts to mitigate phishing attacks, there has been a significant increase in data breaches due to human error. To assist with preventing such attacks, our team has developed a solution... SharkByte. SharkByte is an all-in-one security assessment program designed to test whether there are controls to detect, mitigate, and prevent phishing attacks. SharkByte also highlights the need for log monitoring, providing SOC Analysts with information to mitigate the risk and counter phishing attacks. Organizations can also benefit from SharkByte’s phishing awareness guide, which is designed to train users on identifying phishing attacks. 

To emphasize how easy it is for an attacker to gain full access to a system using phishing techniques, SharkByte utilizes sophisticated attacks using techniques such as Command and Control [C2]. Organizations can engage in the SharkByte assessment program to train users on the risks associated with spear-phishing attacks and increase their overall security posture. 

### SharkBytes Goal:
The primary goal of SharkByte is to grant organizations the knowledge to understand the potential dangers of phishing attacks, and the tools needed to test their defenses against these attacks. Organizations can utilize our SharkByte program to raise awareness for phishing attacks, train users on the dangers of phishing, and test the effectiveness of security controls in place. 

## Exemplary Phishing Engagement using SharkByte:

To showcase Sharkbyte, a simulated cyberattack on a fictional organization (NexusCupcakes) will occur, where a user falls victim to a phishing attack, downloads a malicious document, and establishes a connection to a Command and Control (C2) server. This simulation will demonstrate the potential consequences of employees falling victim to phishing attacks, highlighting the importance of phishing awareness training.

<div align="center">
  <table>
  <tr><th>NexusCupcakes Environment </th><th>Attacker Machines </th></tr>
  <tr><td>
  
  | Machine | Summary of System    |
  | ------------- | -------------  |        
  | NEXUS-DC  | Domain Controller  |               
  | NEXUS-VPN  | OpenVPN Server    |                
  | NEXUS-SPLUNK  | Splunk Server  |
  | NEXUS-USER | OpenVPN Server    |
  | NEXUS-VPN  | User Machine      |
  | NEXUS-WP  | Wordpress Website  | 
  
  </td><td>
  
  | Machine | Summary of System    |
  | ------------- | -------------  |
  | RAWCS-C2  | C2 Server          |
  | RAWCS-KALI  | Attacker Machine |
  </td></tr> </table>
</div>

## Network Topology for Simulated Spear-Phishing Attack:

In this exemplary engagement, NexusCupcakes will gain insight into the value of leveraging tools such as Splunk for enhanced security monitoring and incident response, while also providing users with real-world insight into how Phishing attacks are perpetrated.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d832271a-6cf1-4aee-b90b-6bccd8852a42" width="800" alt="Network Topology">
</p>

During the attack, the C2 server focuses on infiltrating the USER device through a tailored spear-phishing attack - This device is connected to the NEXUSCUPCAKES domain, indicating that an attacker can leverage this attack to gain access to other devices in the domain

### Scope of Phishing Attack:

This attack showcases the sophistication of Spear-phishing, displaying how attackers can leverage these attacks to compromise systems, exfiltrate sensitive data, and execute further malicious actions. It emphasizes the importance of implementing safeguards for effective detection and response, such as log generation designated to C2 compromised through the SIEM solution, Splunk. 

#### Using Phishing Techniques to Achieve Full Compromise through C2 Communication Channel:
1. Adversaries establish a foothold in the targeted machine to initiate an attack. This can be achieved through phishing emails or exploiting vulnerabilities in a system.
2. Once access to the system has been initiated, the attacker can install other malicious software to gain full control over the system.
3. Using a Command and Control Server such as Quasar, attackers can build a communication line with a compromised machine.
4. Once the communication channel is established, the attacker can utilize the C2 channel to initiate malicious activity from the infected machine. The infected system is now considered a zombie of the C2 Server and can now be utilized to perform further attacks such as exfiltrating data, or performing external attacks on other devices such as a Distributed Denial of Service (DDoS) attack. These are just examples; the possibilities are endless once infected by a C2 Server.

Now let's get to work.

## The SharkByte Engagement:

### Step 1 - Finding Hosts that are UP using Active Scanning:
The first step in this engagement is to find hosts that are up, specifically hosts that could be hosting a website. It is important to note that identifying websites is significantly useful when formulating a spear-phishing attack as websites can provide useful information such as employee names, company updates, emails, etc. To accomplish this, nmap can be utilized.

```` bash
nmap -n -sn 10.0.0.0/24 -oG - | awk ‘/Up${print $2}’
````

<p align="center">
  <img src="https://github.com/user-attachments/assets/86948621-9762-4dc6-ab61-62a546f3d5ee" width="700" alt="Nmap Scan">
</p>

### Step 2 - Finding Open Ports using Rustscan:
To spice things up, Rustscan is utilized in conjunction with the addresses obtained from the previous NMAP scan to scan for open ports, specifically services that could potentially be running on port 80 (e.g. WordPress Website). 
```` bash
rustscan --addresses 10.0.0.2,10.0.0.22,10.0.0.54,10.0.0.64,10.0.0.91,10.0.0.136,10.0.0.159,10.0.0.176,10.0.0.202,10.0.0.205 -- -A 
````
Executing this scan displays various open ports. Two addresses that are of interest include 10.0.0.22 & 10.0.0.91.
<p align="center">
  <img src="https://github.com/user-attachments/assets/247a7384-153b-4b2c-80d5-03e5a611c59d" width="700" alt="RustScan">
</p>

### Step 3 - Using Passive Scanning Techniques to View Websites:
Now that we have identified hosts running services on port 80, it is time to check to see whether any of these hosts are running applications/software that could be of interest. Lets first look into the 10.0.0.22 host that was previously identified. Correspondingly, as can be perceived in the screenshot, the 10.0.0.22 host is running Internet Information Services (IIS)
<p align="center">
  <img src="https://github.com/user-attachments/assets/825b355e-411f-490d-9415-9f7e973f229d" width="700" alt="Interesting Find - IIS Server">
</p>

10.0.0.22 did not provide much information and thus, 10.0.0.91 will now be looked into. Correspondingly, viewing http://10.0.0.91 reveals that there is a WAMP Server running on the host, and also shows that there is a WordPress website running on the WAMP Server, http://10.0.0.91/wordpress. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/26e65986-0268-4b0b-aac2-25a7f4b3c54b" width="700" alt="Interesting Find - WAMP Landing Page">
</p>

### Step 4 - Search the WordPress Website for Clues: 
Now that we know that there is a WordPress website running at NexusCupcakes, the next step is to view the website and harvest any information that can be utilized in the Spear-phishing attack. In this case, a search engine on the WordPress website was found. This search bar can be used to search for additional web pages that could potentially provide additional information such as an email. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/25617624-215a-486b-9bce-bcef4ce3b1a6" width="700" alt="Target WordPress Website">
</p>

### Step 5 - Find NexusCupcakes About Us Page:
Using the search bar, characters such as “@” can be searched (searching for @ could potentially reveal email addresses). In this scenario, searching for “@” brought us to the About Us page. After careful inspection of the “About Us” page, it is clear that this webpage does indeed contain email addresses. 

This is a huge security concern, as these email addresses can be utilized during a Spear-phishing attack. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/213f03a4-2043-47ad-93db-0624793c1a32" width="700" alt="Useful Information for Phishing Attack">
</p>

## Weaponization - Command and Control using Quasar:

### Step 1 - Initiate Quasar:
For this attack, we will be using malware created by Quasar. Quasar is an open-source Remote Administration Tool (RAT) that can be used by help desk technicians to remotely access Windows machines for technical assistance. However, Quasar can very easily be used instead as a Remote Access Trojan (also known as RAT) to remotely access a Windows machine without the user’s knowledge or consent. To do this, we will build a client file that will have the appearance of a Microsoft Word document, and send it to the victim through a phishing email. The victim will click the file, mistaking it for a Word document, therefore executing it. Once the client file has been executed, it will start a connection with the attacker machine, allowing the victim machine to be remotely controlled with Quasar. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/d8b2a61e-1d48-44db-bf81-52ed58f5dea5" width="700" alt="Qusar - C2 Server">
</p>

### Step 2 - Create Client file using Client Builder:
To build a client file, we will click on the Builder option in the Quasar GUI. Doing this will show the Basic Settings for the client file. We will use the Client Tag “NexusCupcakes” to identify the victim machine when it initiates the connection. 

By clicking on the Connection Settings tab on the left, we can configure the host that the victim machine will connect to once the client file has been executed. The IP address of the attacker machine is 10.0.0.24, so we will add that as a Connection Host. The port, 4782, will be kept as default. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/a6ee08ed-2ff1-47ad-a9ca-d7e7ab398c3b" width="700" alt="Creating RAT/Zombie File">
</p>

Clicking on the Installation Settings tab on the left will allow us to choose how the RAT will run on the victim machine after the client file has been executed. For this attack, the client file will install itself as a program in a hidden directory called “SubDir” in the victim user’s User Application Data folder.
<p align="center">
  <img src="https://github.com/user-attachments/assets/4b4e8a11-8c67-48ca-a0d6-b03e68a18ace" width="700" alt="Creating RAT/Zombie File">
</p>

### Step 3 - Display Assembly Settings and Sophistication of Creating RAT File:
In the Assembly Settings tab, we can change the Assembly Information of the client file to make it appear as a legitimate file. In this attack, we will make the client file appear as a legitimate MicrosoftWord file by changing the Product Name, File Version, among other settings. We will also change the Assembly Icon to use the Microsoft Word application logo to make the running process seem more legitimate. We will now build the client. 

After naming, building, and saving the client, the client file will appear in the designated save location. The client file has been given the name User-Commitment-Policy-2024.
<p align="center">
  <img src="https://github.com/user-attachments/assets/b76af0b1-336c-42ad-8ae5-30cd02a65a12" width="800" alt="Creating RAT/Zombie File">
</p>

### Step 4 - Start Listening on Quasar for Client Connections:
In Quasar’s Settings, we will press the Start Listening button. This will allow the attacker machine to listen for any victim machines that have executed the client file, allowing us to catch the connection with them. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/4ada9857-8e17-4a09-9fe3-c180afdd0085" width="700" alt="Initiating Quasar">
</p>

## Delivery & Exploitation:

### Step 1 - Send RAT File from QUASAR to User in NexusCupcakes Domain:
Attackers may use a secure email engine such as Protonmail to perpetrate phishing attacks. Correspondingly, the SharkByte program will utilize the emails gathered from the About Us page, in a Spear-phishing attack tailored to NexusCupcakes. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/f8f76a99-1759-4c66-9475-8708d570da33" width="800" alt="Phishing Email">
</p>

Engagement begins with carefully crafted phishing emails tailored to a new User Commitment Policy at NexusCupcakes. This phishing email will contain the RAT file, which in turn will initiate the connection to Quasar upon execution. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/bff1318b-42d3-418e-9aae-279a371d042d" width="700" alt="Phishing Email">
</p>

The NexusCupcakes employee will see an email seemingly sent from the NexusCupcakes IT department. 

After clicking on the email, they will see a message urging NexusCupcakes employees to download and review the attached file. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/0d2c074e-f300-4fa5-8f44-cdd5f8233422" width="700" alt="Phishing Email">
</p>

The victim will download the attachment, believing it to be a document. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/f7c68792-1274-4025-8b42-0a0b47cfe1e7" width="700" alt="Victim Downloading RAT File">
</p>

## Installation of C2 Communication Channel:

### Step 1 - Initiate RAT File:
The victim initiates the DOCX Wrapped RAT file, creating a connection to Quasar Machine. 

In the victim’s download folder, the file will look like a legitimate Microsoft Word document. They will click on it, expecting a document to open. However, nothing apparent will happen. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/b2a7cc55-3fc1-4911-b35c-4cc798bf77d3" width="700" alt="Qusar RAT File">
</p>

## Command and Control:

### Step 1 - Displaying Connection to Victim Machine through Quasar:
After the victim machine has executed the file, the connection will appear in Quasar. The connection captured is with the NEXUS-USER machine, with the IP address of 172.27.232.3. By right-clicking on the connection, we can perform a variety of tasks on the connected machine. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/73f33f35-1335-4172-bc01-2b7054a47d28" width="700" alt="Connection to Victim through Quasar">
</p>

Through “Monitoring” or “User Support” the Remote Desktop function can be utilized. This will allow the attacker full access and visibility to the victim user’s session. Both keyboard and mouse functionality can be enabled for this. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/00fc88b2-d941-4f82-919b-75666cc9dbaf" width="700" alt="Viewing Victims Screen using Quasar">
</p>

## Attack on Objectives - Exfiltration of Data:

Command and Control infections are serious, posing a significant threat(s) to all organizations. Once a machine is compromised by a Command and Control [C2] platform such as Quasar, the attacker can utilize the compromised machine to steal sensitive data (e.g., entire hard drive), pivot to other machines, gain inside intelligence of an organization, and perform additional attacks on other networks.

One of the most preeminent features that Quasar offers is its Keylogger function, allowing whatever the victim types on their device to be captured. With this, the attacker can capture potentially sensitive information that the victim may type, such as passwords or the content of confidential business documents and/or emails. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/80b4e9fb-879e-42a3-9f87-90a542b81128" width="700" alt="Quasar Capabilities">
</p>

Messages can be sent to the victim through the Show Messagebox feature, allowing a popup to appear on the victim’s screen. With this, the attacker can urge the victim to divulge more sensitive information and/or threaten them. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/1ce14d2c-2db3-4207-85b2-d273fd747fea" width="700" alt="Quasar Capabilities">
</p>

The File Manager on the victim machine can also be accessed, allowing the attacker to view, download, upload, and execute files. Other tasks can be performed on the victim machine as well, such as modifying the Registry Editor, remotely executing files, and more. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/1b309cec-41e2-423d-a245-023ae2266e70" width="700" alt="Quasar Capabilities">
</p>

Other actions can be performed without an active user session as well, such as starting or killing processes in Task Manager. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/63d94758-5aee-411b-a196-155a9e2781d1" width="700" alt="Quasar Capabilities">
</p>

## Protecting NeusCupcakes Node Using Splunk:

### Detection of Command and Control Compromise through Splunk:
To help detect potential C2 compromise, we can configure alerts in Splunk to trigger when connections are made with known C2 servers. An alert is configured to trigger whenever a log containing the known C2 server address “10.0.0.24” is collected. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/0360249b-dba0-4e06-8429-93c039963026" width="700" alt="C2 Communication Alert">
</p>

This alert will trigger in real-time for every collected log containing “10.0.0.24”, therefore notifying Splunk admins of the connection. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/63f63cb6-089e-4d70-90bc-11b0750e00da" width="700" alt="C2 Communication Alert">
</p>

The newly created alert can be seen in the Alert menu under Search & Reporting. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/da4dae36-7f9f-4851-bf66-09405f1d8f0f" width="700" alt="C2 Communication Alert">
</p>

After the victim machine is infected by the RAT file, it will start a connection with the C2 server, 10.0.0.24. When this happens, it will trigger the previously created alert. In Activity > Triggered Alerts, we can see all instances of this alert being triggered, indicating that a host has become a victim of C2 compromise. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/e8a03303-6638-4ef0-b42c-3400cef80bd0" width="700" alt="Nmap Scan">
</p>

## Generating Reports of Logs using Splunk:
In Settings > Searches, Reports, and Alerts, we can create a report using the New Report button. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/5e345cc3-fc52-4e25-8018-753e6cb9f486" width="700" alt="Creating Report using Splunk">
</p>

Here we can create a report of all instances of “10.0.0.24” appearing in logs. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/dcb1cbaf-7265-4f4c-81c3-7f4bae65b02c" width="700" alt="Creating Report using Splunk">
</p>

With this report we can get a better look at what device has made the connection, and when. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/a9c67f79-8f87-490d-b424-e12792f818ee" width="700" alt="Viewing C2 Communication through Report">
</p>

## Phishing Awareness Training Program:
engaged clients with a way of gaining real-world experience of how phishing attacks are perpetrated, as well as training that can be utilized to decrease the chances of a successful phishing attack.

In our engagement with NexusCupcakes, NexusCupcakes expressed their need to secure their environment against Command and Control [C2] compromise. Knowing this, RAWCS leveraged a spear-phishing attack in conjunction with C2 compromise, demonstrating how easy it is for an attacker to gain full access to a machine through the click of a few buttons. To combat this, clients engaged in SharkByte are provided with tailored phishing awareness training, corresponding to their needs. NexusCupcakes phishing awareness training can be found by visiting this link—[SharkByte: Phishing Awareness Training](https://docs.google.com/presentation/d/1bt6LExmhYX0TVVxmlY_KLrS1ilkUR_GVl2NxaRxn9p8/edit#slide=id.p1).

In reality, it is quite simple for an attacker to find information such as email addresses of an organization. For example, an attacker can easily navigate through durhamcollege.ca, and find various email addresses of professors, executives, and other members of the Durham College community. If an attacker were to acquire this information, they could formulate a spear-phishing attack designated to Durham College. SharkBytes' goal is to demonstrate this, providing both real-world experience, and tailored phishing awareness training. 

# Lessons Learned & How SharkByte Can Help:
The truth is, anyone can be targeted by a phishing attack. With phishing attacks becoming more sophisticated, organizations must educate their employees on phishing and implement controls to mitigate the risk of compromise. 

SharkByte is designed to simulate a realistic cyberattack on a fictional organization (NexusCupcakes) where a user falls victim to a phishing attack, downloads a malicious document (RAT file), and establishes a connection to the attackers’ Quasar (C2) Server. Phishing attacks are real, and have serious consequences for everyone involved. 

In this engagement, NexusCupcakes will gain insight into the value of leveraging tools such as Splunk for enhanced security monitoring and incident response. SharkByte is designed to highlight the need for log monitoring, providing SOC Analysts with information to mitigate the risk and counter live C2 compromise.

Organizations can also benefit from SharkByte’s phishing awareness guide, which is designed to train users on techniques for identifying a phish through real-world phishing attack scenarios. SharkByte includes a phishing awareness guide, tailored to identifying potential phishing attacks.

Awareness is the first line of defense and our ability to identify a phish is important. You play a critical role and it is important to stay vigilant and knowledgeable about phishing tactics! By doing so, you will be able to prevent yourself from falling victim to a phish. We are SharkByters, after all!

<p align="center">
  <img src="https://github.com/user-attachments/assets/7206d782-f394-4bcf-a523-7c4cf0e20449" width="1200" alt="SharkByte">
</p>
