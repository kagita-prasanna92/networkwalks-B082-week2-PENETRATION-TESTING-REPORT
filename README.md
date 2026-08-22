# networkwalks-B082-week2-PENETRATION-TESTING-REPORT
## 📌 Project Overview-Footprinting, Scanning &amp; Network Discovery
**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>
This report presents the Week 2 activities of my internship at Networkwalks, focusing on network footprinting and network scanning. The activities demonstrate how security professionals gather information about a domain and identify active devices on a network. Kali Linux tools were used for footprinting, while Zenmap was used to scan my own local network. The report documents the commands, results, screenshots, and security significance of the findings.


## 🛠️  Tools Used

 ---
 
| 🛠️ Tool            | ⚡ Purpose                                                                                    |
| ------------------ | ---------------------------------------------------------------------------------------------  |
| 🐉 Kali Linux & Windows         | Operating systems used for reconnaissance and network scanning activities         |
| 🔎 WHOIS                        | Find domain registration details such as registrar, registration dates, and name servers              |
| 🌐 WhatWeb                      | Identify web technologies, server details, CMS, frameworks, and other website components|
| 📡 nslookup                     | Resolve a domain name to its corresponding IP address using DNS                    |
| 📥 curl -I                      | Retrieve and analyse HTTP response headers from the website                        |
| 🛡️ WAFW00F                      | Detect whether a Web Application Firewall (WAF) is protecting the website          |
| 🧭 DNSRecon                     | Enumerate DNS records such as NS, MX, TXT, SPF, and other available records        |
| 🖥️ Zenmap (Nmap GUI)            | Scan the local subnet to identify live hosts, IP addresses, open ports, and MAC addresses|
| ⌨️ Windows CMD                  | Identify the local system's IP address, MAC address, gateway, and network configuration  |

---

## ✍️  **Activities Performed**
**Foot Printing & Reconnaissance**

I conducted a reconnaissance assessment of the networkwalks.com domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, and DNSRecon. Each tool was used to gather a specific type of publicly available information about the target

**WHOIS:** Used to collect domain registration details and identify the associated name servers

**WhatWeb:** Used to identify the technologies and frameworks used by the website. The scan identified WordPress 7.0.4 and WP Download Manager 3.3.58.

**Nslookup:** Used to perform DNS resolution and identify the IP address associated with the domain. The result returned 192.xxx.xxx.xxx

**Curl:** Used to examine the website's HTTP response headers and identify information returned by the web server

**Wafw00f:** Used to determine whether a Web Application Firewall (WAF) is protecting the website

**DNSRecon:** Used to gather available DNS records and identify additional information about the domain's DNS infrastructure

**Curl (-I):** I analyzed the HTTP response headers to gather information about the web server and application. The results also revealed the WordPress REST API endpoint /wp-json/

**Wafw00f:** I checked the target for the presence of a Web Application Firewall. The scan identified ModSecurity (SpiderLabs) as the detected WAF

DNSRecon: I performed DNS enumeration to collect available DNS information, including name servers, mail servers, SPF/TXT records, service records, and DNS software details


## 🔍 **Network Scanning with Zenmap**

The second activity focused on network discovery using Zenmap within my local network. The objective was to determine the local network configuration, identify active devices, collect their IP and MAC addresses, and visualize the network structure.

The process was completed in the following stages:

Network Configuration: The Windows ipconfig command was used to obtain the system's local IP address and subnet information.
Host Discovery: The identified subnet was entered into Zenmap, and the Ping Scan option was selected to locate active devices.
Live Hosts: The scan identified four active hosts:

10.0.0.1/24

**MAC Address Identification:** Zenmap also displayed the corresponding MAC addresses of the discovered hosts.
Network Topology: Finally, the Topology section of Zenmap was opened to visually represent the discovered network devices and their relationships

<img width="1366" height="720" alt="image" src="https://github.com/user-attachments/assets/6f2bd968-2240-4e74-98ff-39b2b902ff93" />


## 🕵️ **Risk Analysis / Impact**

Based on the information gathered during the footprinting and network scanning activities, the following potential security risks were identified:

---

|	Risk & Finding	|Evidence & Observation  |	Potential Impact	| Risk Level |
|	Web technology information exposed |	WhatWeb identified WordPress and WP Download Manager |	Exposed technology details may help attackers identify software that requires further security assessment|	● Medium |
2	Server IP address identifiable	Nslookup resolved the domain to 192.232.216.135.	Reveals the network location of the web service and may assist further reconnaissance.	● Low
3	HTTP technical information exposed	Curl displayed HTTP response headers and the /wp-json/ endpoint.	This information may assist technology fingerprinting and additional enumeration.	● Low
4	WAF technology identifiable	Wafw00f detected ModSecurity (SpiderLabs).	Reveals information about the security mechanisms used by the web application.	● Low
5	DNS infrastructure information exposed	DNSRecon identified DNS, mail, and service-related records.	DNS information can help build a broader picture of the organization's infrastructure.	● Medium
6	Multiple live hosts discovered	Zenmap identified four live hosts on the example local network.	Unrecognized or unauthorized devices could increase the network's potential attack surface.	● Medium

## 🔑 Risk Level Key

🔴 Critical — Severe potential impact
🟠 Medium — Moderate potential impact
🟢 Low — Limited potential impact


**Assessment Note**

The findings above represent observations from the footprinting and network discovery exercises rather than confirmed vulnerabilities. The activities focused primarily on information gathering and host identification; no exploitation or vulnerability validation was performed
