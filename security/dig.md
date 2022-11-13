﻿# Dig

## To run dig (domain information groper)
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