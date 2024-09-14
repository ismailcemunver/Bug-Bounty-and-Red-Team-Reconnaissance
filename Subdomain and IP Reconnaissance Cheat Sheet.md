#### Subdomain Reconnaissance
- **Subfinder:** `subfinder -silent -recursive -all -d domain.com`
- **Amass:** `amass enum -brute -d domain.com -v`
- **Hakrevdns:** `cat ip_addresses.txt | hakrevdns`
- **Dnsx (With ASN):** `echo AS17012 | dnsx -silent -resp-only -ptr`
- **Ffuf:** `ffuf -w /opt/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u http://domain.tld/ -H 'Host: FUZZ.domain.tld' -ic -r -c`
- **Httpx:** `httpx -l subdomains.txt -title -wc -sc -cl -ct -web-server -asn -p 8000,8080,8443,8834,443,80,8008,3000,5000,9090,900,7070,9200,15672,9000 -threads 75 -location > live.txt`
- **Google Dorks**
- **Github Dorks**
- **Shodan**: Manual Shodan dorks, also use `karma_v2`
- **Censys Search**
- **Security Trails**
- **AAD Internals OSINT (for Azure Infrastructure)**

**Additional Notes:**
- Use the tool `anew` to avoid duplicates when saving the output to a file.
- Update the API keys of **Subfinder** and **Amass**.
- Use wordlists of AssetNotes (e.g. commonspeak).
#### IP Reconnaissance
- **Dnsx (IP Adresses):** `subfinder -silent -d domain.com | dnsx -silent -a -resp-only | anew ip_addresses.txt`
- **Asnmap (Find CIDR):** `echo GOOGLE | asnmap`
- **bgp.he.net**
- **Dnsx (to find ASN Numbers):** `subfinder -silent -d hackerone.com | dnsx -silent  -asn`
- **Asnmap (Find with ASN)**: `echo AS32934 | asnmap`
