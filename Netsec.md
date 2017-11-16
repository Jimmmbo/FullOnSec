## Recon and intelligence tools 
### [Masscan](https://danielmiessler.com/study/masscan/)
- Scan the internet in under 6 minutes similair to shodan. Has NMAP functionality for quickly scanning a network

### nslookup
- Name Server lookup
```
nslookup -type=MX example.com
```

### Dig
- Same functionality as nslookup
```
dig *.example.com +short
```

### Nmap
- Used for network scanning and discovery
```
nmap -p 80 -sV -sS -O ta.rg.et.IP
```

### Hping3
- Packet generator. One of the de facto tools for security auditing and testing of firewalls and networks
```
hping3 -c 100 -p 445 -S target.com \ or ta.rg.et.IP
```

### Netcat 
- Great network tool for port listening and establishing a connection to the webserver, scanning, transferring files and can be used as a backdoor
```
nc mail.server.net 25
```

### [Whatweb](https://github.com/urbanadventurer/WhatWeb)
- Identifying a website from SQL errors to which CMS is used etc. Kali has this installed by default
```
whatweb -v www.target.com 
```

### [ZMAP](https://zmap.io/)
- A collection of open source tools for discovery

### [Spiderfoot](http://www.spiderfoot.net/)
- Open Source intelligence automation tool 

### [Internet.nl](https://internet.nl)
- Scan websites for all DNS and TXT records. Find out if they have DMARC, DKIM and SPF + if they use DNSSEC and STARTTLS

### [Panopticlick](https://panopticlick.eff.org/)
- To check if browser is safe against tracking

### [Amiunique?](https://amiunique.org/)
- Check how identifiable you are on the internet 
