# SpiderFoot

## General Information

- [Github Repository](https://github.com/smicallef/spiderfoot)
- [Documentation](https://www.spiderfoot.net/documentation)

## Features

- Query over 100 OSINT sources (IP, domain names, email, names and more)
- Select the target, pick modules and spiderfoot will collect and build links
- You can identify data leaks, vulnerabilities or sensitive information
- Windows and Linux

## Needed API Keys

- Honeypot Checker
- Shodan
- VirusTotal
- IBM X-Force Exchange
- MalwarePatrol
- BotScout
- Cymon.io
- Censys.io
- Hunter.io
- AlienVault OTX
- ClearBit
- BuiltWith
- FraudGuard
- IPinfo.io
- CIRCL.LU
- SecurityTrails
- FullContact.com
- RiskIQ
- Citadel.pw

### API Keys needed and what API keys can be usefull

https://twitter.com/spiderfoot/status/1390783197873586183?s=19

## Starting

```bash
# Start a server on localhost:5001
python ./sf.py
```

```bash
# CLI possible
python ./sfcli.py --help
```

```bash
# You can also use it remotely
python ./sf.py <externalIP>
python ./sf.py 0.0.0.0:5001
python ./sfcli.py -u http://<remote ip>:5001
```

## Using Spiderfoot

### Initiate new scans

Need name and target (domain, ip, subdomain, subnet)

- By Use Case
- By Required Data
- By Module (more advanced)

No dependency checking with module scanning, if one module need others module result, you won't get any data.

### Scan result

- Bar chart (clickable)

### Browsing results

- Searchable results
- Data type - Checkbox : set/unset as false positive (orange button)
- Black icon to change display

### Searching results

- You can search at the entire scan level or by data type
   - Exact Value
   - Pattern Matching - Simple pattern (`*:22`)
   - Regex search - Classic string regex (` '/\d+.\d+.\d+.\d+/'`)

## Modules

- When a module gets a data, this one is transmitted to other potentially interested modules
- They will process it and generate new events, maybe find others data.. And so on
- All modules works with data types
   - entities - Like IP, hostnames etc
   - subentities - Like port numbers, URLs etc
   - descriptors - Description of these entities
   - data - Mostly unstructured data (web page content...)

