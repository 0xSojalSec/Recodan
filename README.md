<h1 align="center">Recodan</h1>


`Recodan extracts IPs from Shodan searches. just the IPs you need.`


- Extract IPs from Shodan
- Random User-Agent rotation
- Clean, pipe-friendly output
- Zero dependencies (just bash & curl)


<br>
<br>

`installation`
> `oneliner`
```bash
git clone https://github.com/0xSojalSec/Recodan.git && cd Recodan && chmod +x Recodan.sh && sudo mv Recodan.sh /bin/Recodan && cd .. && rm -rf Recodan
```

<br>
<br>

`arguments`
<pre>
  -q   : Search query (required)
</pre>

<br>
<br>

`example commands`
```bash
Recodan -q "apache" > apache_ips.txt # Search for apache servers
```
```bash
Recodan -q 'org:\"Google LLC\"' # Search with organization filter
```
```bash
Recodan -q "port:443" | sort -u # Search with port filter
```
```bash
Recodan -q "apache" | xargs -I {} nmap -sV {} # Scan found IPs with nmap
```
```bash
Recodan -q "apache" | tee ips.txt | wc -l # Save to file and count results
```
```bash
Recodan -q "apache" | grep -v "^10\." > public_ips.txt # Filter and process results
```



