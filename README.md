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

1. **Azure Data Breach (Phishing)** - In February 2024, Microsoft suffered from the largest data breach recorded. The success of this attack stemmed from phishing. Threat actors embedded malicious documents into emails that led victims to phishing websites. This attack targeted mid and senior-level company executives...
   
3. **MGM Resorts Data Breach (Vishing)** -  In September 2023, a well-respected hotel and casino chain, suffered a Vishing attack launched by APT ALPHV and Scattered Spider. The success of this attack stemmed from a Vishing attack, in which the attacker called MGM IT Help Desk requesting assistance with an account. Credentials were provided, which led to the attacks gaining administrator privileges to MGM’s Azure and Okta tenant environments...

With phishing being centered around human error, it is evident that something must be done to help decrease the success rate of phishing. 

## Getting to know the SharkByte Phishing Assessment Program:
Despite organizations’ ongoing efforts to mitigate phishing attacks, there has been a significant increase in data breaches due to human error. To assist with preventing such attacks, our team has developed a solution... SharkByte. SharkByte is an all-in-one security assessment program designed to test whether there are controls to detect, mitigate, and prevent phishing attacks. SharkByte also highlights the need for log monitoring, providing SOC Analysts with information to mitigate the risk and counter phishing attacks. Organizations can also benefit from SharkByte’s phishing awareness guide, which is designed to train users on identifying phishing attacks. 

SharkByte includes a phishing awareness guide, tailored to identifying potential phishing attacks. In summary, SharkByte aims to demonstrate the full impact of a phishing attack through a Command and Control infection, allowing organizations to understand why it is important to have the necessary controls in place to detect, mitigate, and prevent such attacks

To emphasize how easy it is for an attacker to gain full access to a system using phishing techniques, SharkByte utilizes sophisticated attacks using techniques such as Command and Control [C2]. Organizations can engage in the SharkByte assessment program, to both train users on the risks associated with spear-phishing attacks, as well ass increase their overall security posture. 

### SharkBytes Goal:
The primary goal of SharkByte is to grant organizations the knowledge to understand the potential dangers of phishing attacks, and the tools needed to test their defenses against these attacks. Organizations can utilize our SharkByte program to raise awareness for phishing attacks, train users on the dangers of phishing, and test the effectiveness of security controls in place. 

## Exemplary Phishing Engamgent using SharkByte:

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
To spice things up, Rustscan is utilized in conjkuction with the addresses obtained from the previous NMAP scan to scan for open ports, specifically services that could potentially be running on port 80 (e.g. WordPress Website). 
```` bash
rustscan --addresses 10.0.0.2,10.0.0.22,10.0.0.54,10.0.0.64,10.0.0.91,10.0.0.136,10.0.0.159,10.0.0.176,10.0.0.202,10.0.0.205 -- -A 
````
Executing this scan displays various open ports. Two addresses that are of interest include 10.0.0.22, 10.0.0.91, and 10.0.0.159. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/247a7384-153b-4b2c-80d5-03e5a611c59d" width="700" alt="Nmap Scan">
</p>


