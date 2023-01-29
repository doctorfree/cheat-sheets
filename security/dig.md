# Dig

`Dig` stands for **Domain Information Groper**. Dig is a network administration command-line tool for querying [Domain Name System (DNS)](../networking/dns.md) name servers. It is useful for verifying and troubleshooting DNS problems and also to perform DNS lookups and displays the answers that are returned from the name server that were queried. Dig is part of the BIND domain name server software suite. The `dig` command replaces older tool such as `nslookup` and `host`. The `dig` tool is available in all major Linux distributions.

When a specific name server is not specified in the command invocation, it uses the operating system's default resolver, usually configured in the file `resolv.conf`. Without any arguments it queries the DNS root zone.

Dig supports Internationalized domain name (IDN) queries.

Dig is a component of the domain name server software suite [BIND](../networking/bind.md).

## To run dig
```shell
dig [domain]
```

## To just get the ip address
```shell
dig [domain] +nocomments +noauthority +noadditional +nostats 
dig [domain] +noall +answer
dig [domain] +short
```

## To use a specific query type
```shell
dig -t [query type] [domain] [options]
dig [domain] [query type] [options]
```

## To view ALL DNS record types use query ANY
```shell
dig -t ANY [domain] [options]
dig [domain] ANY [options]
```

## To do a DNS reverse look up 
```shell
dig -x [ip address] +short
```

## To use a specific DNS server
```shell
dig @[specific DNS] [domain]
```

## To do a bulk DNS query (where file.txt has all the domains, one to a line)
```shell
dig [domain1] [options] [domain2] [options]
dig -f file.txt [options]
```

## Common usage examples

- What is the website's IP address?
    ```shell
    dig apple.com
	```
- How do you identify the name servers associated with a domain?
    ```shell
    dig NS apple.com +short
    dig NS com. +short
	```
- Which eMail Servers are responsible for a domain?
    ```shell
    dig MX apple.com +short
	```
- Finding out the domain name associated with the IP address (reverse IP lookup)
    ```shell
    dig -x 1.1.1.1 +short
    dig -x 8.8.4.4 +short
	```
- Finding out the delegation path for any DNS zone (learn how DNS works)
    ```shell
    dig apple.com +trace
	```
- Finding out DNS answers from specific cache resolver (e.g. Cloudflare [1.1.1.1], Google DNS [8.8.8.8], IBM and so on for cyberciti.biz domain)
    ```shell
    dig A cyberciti.biz @1.1.1.1 +short
    dig A cyberciti.biz @8.8.8.8 +short
	```
- Finding out the cache expire time (TTL) for DNS
    ```shell
    dig A www.cyberciti.biz +nocmd +noall +answer +ttlid
    dig AAAA www.cyberciti.biz +nocmd +noall +answer +ttlid
	```
- Finding if a zone is synchronized with all authoritative name servers (look for serial number)
    ```shell
    dig nixcraft.com +nssearch
	```
- What is my public IPv4 or IPv6 address?
    ```shell
    dig TXT o-o.myaddr.l.google.com @ns1.google.com +short
    dig TXT ch whoami.cloudflare @1.0.0.1 +short
	```
- Getting help about the dig command
    ```shell
    man dig
	```

```shell
# Get the address(es) for yahoo.com
dig yahoo.com A +noall +answer

# Get a list of yahoo's mail servers
dig yahoo.com MX +noall +answer

# Get a list of DNS servers authoritative for yahoo.com
dig yahoo.com NS +noall +answer

# Get all of the above
dig yahoo.com ANY +noall +answer

# More obscurely, for the present anyway, you can also poll for a host's IPv6 address using the AAAA option.
dig www.isc.org AAAA +short

# If the domain you want to query allows DNS transfers, you can get those, too. The reality of life on the Internet, however, is that very few domains allow unrestricted transfers these days.
dig yourdomain.com AXFR
```

## Additonal resources

- [Dig HowTo](https://www.madboa.com/geek/dig/)
