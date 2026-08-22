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

WHOIS: Used to collect domain registration details and identify the associated name servers
WhatWeb: Used to identify the technologies and frameworks used by the website. The scan identified WordPress 7.0.4 and WP Download Manager 3.3.58.
Nslookup: Used to perform DNS resolution and identify the IP address associated with the domain. The result returned 192.232.216.135
Curl: Used to examine the website's HTTP response headers and identify information returned by the web server
Wafw00f: Used to determine whether a Web Application Firewall (WAF) is protecting the website
DNSRecon: Used to gather available DNS records and identify additional information about the domain's DNS infrastructure
Curl (-I): I analyzed the HTTP response headers to gather information about the web server and application. The results also revealed the WordPress REST API endpoint /wp-json/
Wafw00f: I checked the target for the presence of a Web Application Firewall. The scan identified ModSecurity (SpiderLabs) as the detected WAF
DNSRecon: I performed DNS enumeration to collect available DNS information, including name servers, mail servers, SPF/TXT records, service records, and DNS software details


## **Network Scanning with Zenmap**
