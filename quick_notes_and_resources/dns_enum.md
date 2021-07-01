## DNS Enumeration and Zone Transfers

### DNS Enumeration
Either of the following commands can be used to obtain name server information that belongs to the `<domain name>`
* `> nslookup -q=ns <domain name>` 
* `> host -t ns <domain name>` 	

### DNS Lookup
#### Forward DNS lookup 
you can create `names.txt` file that includes specific names that you're interested in. The following is an example for `names.txt` file content.  
```
www
ftp
mail
proxy
```

And via command line, you can loop over the names to find out if subdomains exist: 
```
> for n in $(cat names.txt); do host $n.<domain name>;done
```

#### Reverse DNS lookup 
To find PTR records in `<domain name>`, you can call `host` with `<host ip>.ip` by looping over a range. In the following example the range is between 1 and 10 and `"not found"` records are excluded via `grep -v`   
`for ip in $(seq 1 10);do host <host ip>.$ip;done | grep -v “not found”`



### Zone Transfer Attempts
Either of the following commands can be used to attempt insecure zone transfers for `<domain name>`:
* `> host -l <domain name> <name server name>` 
* `> dnsrecon -d <domain name> -t axfr`
* `> dnsenum <domain name>`

