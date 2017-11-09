## Scanning 
### [Masscan](https://danielmiessler.com/study/masscan/)
- Scan the internet in under 6 minutes similair to shodan. Has NMAP functionality for quickly scanning a network

### NSlookup
- Name Server lookup
```
nslookup -type=MX example.com
```

### Dig
- Same functionality as the nslookup
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
hping3 -c 100 -p 445 -S target.com oor ta.rg.et.IP
```

### [ZMAP](https://zmap.io/)
- A collection of open source tools for discovery
