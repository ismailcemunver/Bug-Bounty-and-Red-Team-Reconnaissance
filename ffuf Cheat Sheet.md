#### Directory Fuzzing with Saved HTTP Request
```
ffuf -w /opt/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -request <savedRequestFile> -request-proto http -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <filterResponseSize>
```
#### Directory Fuzzing with Saved HTTPS Request
```
ffuf -w /opt/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -request <savedRequestFile> -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <filterResponseSize>
```
#### Virtual Host Fuzzing

```shell-session
ffuf -w /opt/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u http://domain.tld/ -H 'Host: FUZZ.domain.tld' -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <filterResponseSize>
```
#### Directory Fuzzing
```
ffuf -w /opt/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u http://domain.tld/FUZZ -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <filterResponseSize>
```
#### Recursive Fuzzing

```shell-session
ffuf -w /opt/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u http://domain.tld/FUZZ -recursion -recursion-depth 1 -e .aspx -v -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599
```
#### Extension Fuzzing
```shell-session
ffuf -w /opt/SecLists/Discovery/Web-Content/web-extensions.txt:FUZZ -u http://domain.tld/indexFUZZ -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <responseSizeToFilter>
```
#### Fuzzing With Extension
```shell-session
ffuf -w /opt/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u http://domain.tld/FUZZ.php -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <responseSizeToFilter>
```
#### Subdomain Fuzzing

```shell-session
ffuf -w /opt/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u https://FUZZ.domain.tld/ -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <responseSizeToFilter>
```
#### GET Request Fuzzing

```shell-session
ffuf -w /opt/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u http://domain.tld?FUZZ=test -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <responseSizeToFilter>
```
#### POST Request JSON Fuzzing
```shell-session
ffuf -w /opt/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u http://domain.tld/directory -X POST -d '{"FUZZ":"test"}' -H 'Content-Type: application/json' -ic -r -c -mc 200-299,301,302,307,401,403,405,500-599 -fs <responseSizeToFilter>
```
