# Recon 💻

## Nmap:

- Nmap (Network Mapper) is an essential tool in the bug bounty world for several reasons:

1. Host Discovery: Nmap allows you to identify active devices on a network, which is crucial for mapping the target environment.

2. Port Scanning: You can scan open ports on a host to identify services and applications that might be vulnerable.

3. Version Detection: Nmap can determine the versions of services running on open ports, which helps in identifying specific vulnerabilities.

4. Operating System Fingerprinting: Nmap can guess the operating system of the target host, providing additional information that can be useful for finding vulnerabilities.

5. Custom Scripts: Using the Nmap Scripting Engine (NSE), you can run custom scripts to detect specific vulnerabilities and automate security tasks. These capabilities make Nmap a powerful tool for security researchers looking to identify and exploit vulnerabilities in bug bounty programs.

Legal Issues | Nmap Network Scanning

https://nmap.org/book/legal-issues.html

nmap -A -F -T1 10.10.10.223 -v

-A: Enables all detection options, including service versions, scripts, and more. 

-F: Performs a fast scan of the most common ports (100 by default). 

-T1: Sets the scan speed to "slow," which can be useful to avoid detection. 

-v: Increases the verbosity of the command, providing more information about the scan.


## Ffuf:

- FFUF (Fuzz Faster U Fool) is a fuzzing tool used in bug bounty programs to find vulnerabilities in web applications. Here’s how it can be useful:

1. Directory and File Fuzzing: FFUF can search for hidden directories and files in a web application, helping to identify potential entry points for attacks.

2. Input Injection Testing: By sending a large number of random inputs to the application, FFUF can detect input validation issues and other security errors.

3. Fast and Flexible Scanning: FFUF is quick and allows you to specify inputs and parameters for requests, making it easier to detect specific vulnerabilities.

4. Response Analysis: FFUF analyzes server responses to identify unusual behaviors or errors that might indicate a vulnerability.

5. Using FFUF in a bug bounty program allows you to discover vulnerabilities that might have gone unnoticed with other testing methods, thus improving the application's security.

ffuf -w /usr/share/wordlists/dirb/common.txt -u http://tenet.htb/FUZZ -p 1

SecLists

https://github.com/danielmiessler/SecLists


## Shodan:

- Shodan is a powerful tool for bug bounty programs because it allows for efficient network reconnaissance. Here's how it can be useful:

1. Search for Exposed Services: Shodan lets you search for devices and services exposed on the Internet, such as web servers, open ports, IoT devices, etc.

2. Vulnerability Identification: By finding exposed devices and services, you can analyze if they have known vulnerabilities that could be exploited.

3. Infrastructure Mapping: It helps map an organization's infrastructure, identifying hosts and services that could be potential targets.

4. Misconfiguration Detection: You can find devices with misconfigurations or insecure settings that could be exploited.

5. Search Automation: With Shodan, you can automate searches using specific queries to quickly find vulnerable hosts.

6. Using Shodan in a bug bounty program allows you to identify and prioritize potential targets, improving your chances of finding significant vulnerabilities.

- (Get API key from Web/Account)

- Terminal:

- shodan init (API key)

- shodan info (Credits available in the account)

- shodan -h (Help)

- shodan count wordpress 1.4.7 (The command shodan count wordpress 1.4.7 is used to search Shodan for the number of web servers running version 1.4.7 of WordPress. This can be useful in a bug bounty program to identify potential targets that might be running a vulnerable version of WordPress.)

- shodan download wordpressfile “wordpress 1.4.7” (Downloads a json.gz file) (The command shodan download wordpressfile "wordpress 1.4.7" is used to search Shodan for files related to WordPress version 1.4.7 and download them. This can be useful in a bug bounty program to analyze the specific version for potential vulnerabilities.)

### Gunzip:

- Gunzip File.jason.gz (unzip .gz file)

### Gedit:

- sudo apt install gedit (Install Gedit)

- gedit File.jason.gz (Edit file)

### Beautify:

https://codebeautify.org/jsonviewer

- Beautify JSON is a very useful tool for formatting and beautifying JSON data. Here are some of its main applications:

1. Formatting JSON: Converts JSON data into a more readable and organized format, adding spaces and line breaks to improve readability.

2. Validating JSON: Checks if the JSON data is valid and corrects errors if necessary.

3. Visualizing JSON: Displays JSON data in a hierarchical view, making it easier to navigate and understand the structure of the data.

4. Debugging: Makes it easier to identify and fix errors in your JSON data.

5. Compatibility: Facilitates working with APIs that use JSON, making the data easier to read and handle.

- These functions are especially useful for developers and people who work with APIs, as they help to analyze, debug, and better understand JSON data.

- (Copy the info in the file.jsonwith gedit and paste it in the Beautify JSON web tool, then press Beautify to properly read the content.)

- host yahoo.com (gives us a range of IP addresses that are running on yahoo.com)

- ping yahoo.com (gives us the IP addresses that we are able to ping)

### Burp suit:

Open burp suit/proxy/intercept
open website look for www.yahoo.com
and we ccan see in the request the IP reached for the especific domain.

- shodan host IP (It will give us this information): City, Country, Organization, Updated, Number of open ports, Ports information, Ports, SSL Versions.

- shodan scan submit IP (To Scan a network)

# Hurricane Electric

- The BGP.he.net website is a tool created by Hurricane Electric primarily used to obtain information related to 
  the global Internet routing system based on the BGP (Border Gateway Protocol). This site is widely used by 
  network administrators, researchers, and cybersecurity professionals to perform network analysis. Its main 
  features are:

1. Information about ASN (Autonomous System Numbers):
   Displays details about autonomous systems (AS), such as their announced prefixes, peers (BGP connections with 
   other ASes), routes, and the history of network changes.

2. IP Prefix Exploration:
   Allows users to search for IP address ranges and see which AS manages them, along with the associated information.

3. Peering Status:
   Provides statistics on BGP connections between different ASes, including details of who is announcing routes and 
   to where.

4. BGP Route Monitoring:
   Helps track how routes propagate across the Internet and detect issues such as unreachable or misconfigured 
   routes.

5. Historical Information:
   Offers a history of changes in IP prefixes and routing configurations, useful for audits or investigating 
   connectivity problems.

6. Global Statistics:
   Includes charts and tables with data on the number of globally announced prefixes, ASN growth, and other key 
   metrics of the Internet ecosystem.

7. Peering Verification on the "Hurricane Electric IPv6 Peering Portal":
   If you have an account, you can use the site to manage or verify peering connections with Hurricane Electric.

8. Example of Use:
   If you enter an AS number (such as AS15169 for Google), you will get complete information about the IP prefixes 
   it manages, its peers, and the routes it announces.

9. Applications:

  - Network troubleshooting: For issues such as outages or route misconfigurations.
  - Peering planning: Identify potential partners for BGP connections.
  - Security and forensic analysis: Investigate routing anomalies, such as BGP hijacking attacks.
  - Infrastructure studies: Explore the global Internet topology at a high level.

https://bgp.he.net/

# Shodan Dashboard:

- org Yahoo (To find the organization Yahoo)
- IP Address (will pull down all this information): Geneal information, Web technologies, Open ports
- product:Apache (To see which company use that product and check versions and if they have vulnerabilities)

- You have lots of examples in Dashboard/Search query Examples.

# To take notes use CherryTree

![Captura de pantalla 2024-11-20 192429](https://github.com/user-attachments/assets/cf0b701d-ae59-4f06-8697-e7b87e2c75c0)

# Diferent parts of a URL:

![Captura de pantalla 2024-11-20 192543](https://github.com/user-attachments/assets/589c5007-0ce7-4691-a103-86a93f90e1f2)

https:// (Protocol)

sub = WWW (subdomain) You can Ffuf with wffuf

domain (Domain)

com (Top domain level)

blog/artical/search (Pathor location of content)

blog (Directory) You can Ffuf Directorys Here

artical (Directory)

search (Page)

? (signifies a query)

param=42 (parameter) You can start to mess around changing things  url=42 / id=42


# How DNS works:

https://howdns.works/

# DIG:

example to use dig: 

dig axfr @ friendzone.red

to save results in a file:

dig axfr @ friendzone.red > zone

to add more:

dig axfr @ friendzoneportal.red >> zone

It will show where friendzone is:

cat zone | grep friendzone

cat zone | grep friendzone | grep IN | awk '{print $1}' | sort -u 

*REMEMBER: Port 53 is used for zone transfer

To get more info about companies:

nslookup www.google.com
whois google.com

# The Harvester:

(to find domains, subdomains & email address)

theHarverter -d domain.com -b google

# Crt.sh

(To check subdomains) make sure that urls are in scope before start

https://Crt.sh

Important subdomains dev, admin, api

# Wayback Machine

https://web.archive.org/

Companies host domains or subdomains that are no longer in use and no updated, so we can find vulnerabilities or cve

amass enum -passive -d yahoo.com (find subdomains)

gedit yahoo.txt (paste them in this file)

cat yahoo.txt | ./waybackurls > yahoo.urls (will tell us the valids urls from the file)

wc -l yahoo.urls (will show us how many are valid)

sudo apt install httprobe

cat yahoo.txt | httprobe -t 1000 > valid.urls (will save all the valid urls into a file)

sudo apt install sublist3r

sublist3r -d yahoo.com (find subdomains)

amass enum -passive -d yahoo.com (find subdomains)

# Wappalyzer: (Find web technology)

CMS, Programming language, Oparating systems, Blogs, Font scripts, Web servers, WordPress themes, etc...

# React Development tools: (Find is is using React)

# W3Techs: (Find web technology)

[https://w3techs.com/](https://w3techs.com/sites)

# Inspect web:

Go to the web, right cick and press inspect

Go to Debugger

wp-includes/js

JS wp-embed.min.js

press {} prety print at the bottom and look through to find something.

# Nmap:

nmap -A -p35, 445, 135, 138, 80, 443  -v (use it only to specific ports)

# Fuff:

ffuf -u https://FUZZ.yahoo.com/ -w /usr/share/wordlists/dirb/common.txt -p 1 (to check domains)

ffuf -u https://FUZZ.yahoo.com/ -w /usr/share/wordlists/dirb/common.txt -p 1 -fc 301

ffuf -u https://yahoo.com/FUZZ -w /usr/share/wordlists/dirb/common.txt -p 1 -fc 301 (to check subdomains)

ffuf -u https://api.yahoo.com/FUZZ -w /usr/share/wordlists/dirb/common.txt (to check valid endpoint)

#Dirb: (Another fuzzer)

dirb https://yahoo.com

# wpscan: (to check wordpress vulnerabilities)

wpscan --url http://tenet.htb -e ap --plugins-detection aggressive


