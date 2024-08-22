<p align="center">
  <img src="https://github.com/user-attachments/assets/9510e919-84f0-471b-998b-47c7b8d199ff" width="350" alt="SharkByte Logo">
</p>

![Static Badge](https://img.shields.io/badge/Release_Date-April_2024-Blue?color=blue) ![Static Badge](https://img.shields.io/badge/Contributors-Christos_Kappos_%26_Willow_Ersil-Green?labelColor=grey&color=green) ![Static Badge](https://img.shields.io/badge/Purpose-Let's_Scrap_Phishing-Blue?color=blue)

<h1 align="center">SharkByte: Human Error's Worst Nightmare</h1>
<p align="center">
  An all-in-one service designed to test whether there are controls to mitigate and combat a phishing attack.
</p>

## What is Phishing?
Phishing relies on human error, exploiting our curiosity, and taking advantage of users who let their guard down with minimal effort. Instead of utilizing sophisticated tools throughout the kill chain, phishing can be used to gain access to a victim's system through simple social engineering tactics. 

This often includes tactics such as persuading an individual to open a link, leading to a malicious website, or persuading an individual into downloading and executing/opening a program. 

![image](https://github.com/user-attachments/assets/d7ac49de-43e2-4923-aeaf-ad8dbd7da5a5)

Phishing is relatively easy to execute, so both amateur and experienced cybercriminals rely on this technique. 

## The Proliferation of Phishing:
The ever-growing increase in successful organizational compromise using phishing techniques has significantly increased. In 2024, there were various successful phishing cases, with some of the more critical cases including:

1. **Azure Data Breach (Phishing)** - In February 2024, Microsoft suffered from the largest data breach recorded. The success of this attack stemmed from phishing. Threat actors embedded malicious documents into emails that led victims to phishing websites. This attack targeted mid and senior-level company executives...
   
3. **MGM Resorts Data Breach (Vishing)** -  In September 2023, a well-respected hotel and casino chain, suffered a Vishing attack launched by APT ALPHV and Scattered Spider. The success of this attack stemmed from a Vishing attack, in which the attacker called MGM IT Help Desk requesting assistance with an account. Credentials were provided, which led to the attacks gaining administrator privileges to MGM’s Azure and Okta tenant environments...

With phishing being centered around human error, it is evident that something must be done to help decrease the success rate of phishing. 

## SharkByte Phishing Assessment Program:
Despite organizations’ ongoing efforts to mitigate phishing attacks, there has been a significant increase in data breaches due to human error. Organizations seeking guidance on decreasing the risk of being subject to a successful Spear-phishing attack may find SharkByte appealing. 

SharkByte is designed to demonstrate the full impact of a phishing attack through a simulated Command & Control [C2] compromise, allowing organizations to understand why it is important to have the necessary controls in place to detect, mitigate, and prevent such attacks. 

SharkByte also highlights the need for log monitoring, providing SOC Analysts with information to mitigate the risk and counter phishing attacks. Organizations can also benefit from SharkByte’s phishing awareness guide, which is designed to train users on identifying phishing attacks. 

With SharkByte emphasizing Spear-phishing, and Command and Control [C2] post-exploitation, organizations can engage in RAWCS’ SharkByte Assessment Program, to both train users on the risks associated with successful Spear-phishing attacks and increase their overall security posture. 

To showcase SharkByte, a fictional company running an on-premise Active Directory environment with the domain nexuscupcakes.corp will be utilized. 
NexusCupcakes enviornment includes:

| Machine | Summary of System    |
| ------------- | -------------  |
| NEXUS-DC  | Domain Controller  |
| NEXUS-VPN  | OpenVPN Server    |
| NEXUS-SPLUNK  | Splunk Server  |
| NEXUS-USER | OpenVPN Server    |
| NEXUS-VPN  | User Machine      |
| NEXUS-WP  | Wordpress Website  |

## Exemplary Phishing Engamgent using SharkByte:
In this exemplary engagement, NexusCupcakes will gain insight into the value of leveraging tools such as Splunk for enhanced security monitoring and incident response, while also providing users with real-world insight into how Phishing attacks are perpetrated.

### Scope of Phishing Attack:

This attack showcases the sophistication of Spear-phishing, displaying how attackers can leverage these attacks to compromise systems, exfiltrate sensitive data, and execute further malicious actions. It emphasizes the importance of implementing safeguards for effective detection and response, such as log generation designated to C2 compromised through the SIEM solution, Splunk. 






