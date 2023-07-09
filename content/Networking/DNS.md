---
tags: [networking]
title: Domain Name Server (DNS)
aliases: [Domain Name Server (DNS)]
linter-yaml-title-alias: Domain Name Server (DNS)
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:42 am
---
# Domain Name Server (DNS)
#networking 

Domain Name System (DNS) is a service which handles converting a domain name into a routable[#Internet Protocol IP address](#Internet%20Protocol%20IP%20address), allowing your personal computer to access the specific servers.

## Internet Protocol (IP) address
It is the unique identifier of each computer in a network to allow communication between them

### IPv4
Address space with 32 bits with upto 4,294,967,296 available addresses


### IPv6
Address space is 128-bits long with 340 undecillion ips.


## Domain Registrars
Domain registrars are authorities who have the ability to assign domain names under one or more top-level domains.

Domains get registered through InterNIC, Which is a service provided by the Internet Corporation (ICANN), and enforces the uniqueness of domain names all over the internet.

After registration all domain names can be found publicly in a central WhoIS database.


## Top-Level Domains

The last work with a domain name represents the top-level domain name eg: `example.com`

the second word within a domain name is known as the second-level domain name eg `example.co.uk`


Top-level domain names are controlled by the Internet Assigned Numbers Authority (IANA)

All available top level domains are stored in a publicly available database at:
http://www.iana.org/domains/root/db



## Start of Authority (SOA)

Every domain must have a SOA record. The SOA is a way for the Domain Admins to provide information about the domain eg. how often it is updated, what is the admin's email address and etc.

## What is a DNS SOA record?

The [DNS](https://www.cloudflare.com/learning/dns/what-is-dns/) ‘start of authority’ (SOA) record stores important information about a [domain](https://www.cloudflare.com/learning/dns/glossary/what-is-a-domain-name/) or [zone](https://www.cloudflare.com/learning/dns/glossary/dns-zone/) such as the email address of the administrator, when the domain was last updated, and how long the server should wait between refreshes.

All DNS zones need an SOA record in order to conform to IETF standards. SOA records are also important for zone transfers.

Example of an SOA record:

---------
| Name:       |     example.com                |
| ----------- | -------------------- |
| record type | SOA                  |
| MNAME       | ns.primaryserver.com |
| RNAME       | admin.example.com    |
| SERIAL      | 1111111111           |
| REFRESH     | 86400                |
| RETRY       | 7200                 |
| EXPIRE      | 4000000              |
| TTL         | 11200                |
|             |                      |


## A Records
Address Records are one of the fundamental types of DNS records

An A Record allows you to convert the name of a domain directly into an [#Internet Protocol IP address](#Internet%20Protocol%20IP%20address). They can also be used on the root(naked domain name) itself.

## CNAME Records
Canonical Names (CNAMES) are another fundamental DNS record used to resolve one domain name to another - rather than an IP address.


## NS Records
Name Server Records (NS) are used by the top-level domain servers to direct traffic to the DNS server containing the authoritative DNS records. Usually 2-4 records are provided for redundancy.

## TTL

Tile to Live (TTL) is the length of time that a DNS record gets cached on the resolving server or the users own local maching

The lower the TTL - the faster that changes to the DNS records will propagate across the internet.

TTL is always measured in seconds under IPv4.




