# OSINT

[Open Source Intelligence](https://en.wikipedia.org/wiki/Open-source_intelligence)
(OSINT) is the collection and analysis of data gathered from open sources
(covert sources and publicly available information; PAI) to produce actionable
intelligence. OSINT is primarily used in national security, law enforcement,
and business intelligence functions and is of value to analysts who use
non-sensitive intelligence in answering classified, unclassified, or proprietary
intelligence requirements across the previous intelligence disciplines.

## Table of Contents

- [OSINT Framework](#osint-framework)
- [OSINT Tools](#osint-tools)
  - [Malware Information Sharing Platform](#malware-information-sharing-platform)
  - [SpiderFoot](#spiderfoot)
  - [Shodan](#shodan)
  - [urlscan.io](#urlscan.io)
  - [Maltego](#maltego)
  - [Recon-ng](#recon-ng)
  - [IntelOwl](#intelowl)
  - [DNS Twister](#dns-twister)
  - [Online Cameras](#online-cameras)
  - [IP Logger](#ip-logger)
  - [People Search](#people-search)
  - [ImgOps](#imgops)
- [OSINT Kasm Workspace](#osint-kasm-workspace)

## OSINT Framework

The [OSINT Framework](https://osintframework.com) is focused on gathering
information from free tools or resources. The intention is to help people
find free OSINT resources. Some of the sites included might require registration
or offer more data for $$$, but you should be able to get at least a portion
of the available information for no cost.

The `OSINT Framework` provides a much more exhaustive and well organized list
of `OSINT` tools and resources. This is the number one best `OSINT`
meta-resource and includes links to most of the tools listed below.

## OSINT Tools

These are but a few of the freely available tools widely used in the
gathering of open source intelligence. See the
[OSINT Framework](https://osintframework.com) for a more exhaustive list.

### Malware Information Sharing Platform

[MISP](misp.md) threat sharing
(`Malware Information Sharing Platform`) is an open source threat intelligence
platform. The project develops utilities and documentation for more effective
threat intelligence, by sharing indicators of compromise. There are several
organizations who run MISP instances listed on the website.

### SpiderFoot

[SpiderFoot](https://github.com/smicallef/spiderfoot) automates OSINT for
threat intelligence and mapping your attack surface.  It integrates with
just about every data source available and utilises a range of methods for
data analysis, making that data easy to navigate.

SpiderFoot has an embedded web-server for providing a clean and intuitive
web-based interface but can also be used completely via the command-line.
It's written in Python 3 and MIT-licensed.

### Shodan

[Shodan](https://www.shodan.io) is a search engine that lets users search for
various types of servers (webcams, routers, servers, etc.) connected to the
internet using a variety of filters.[1] Some have also described it as a search
engine of service banners, which are metadata that the server sends back to the
client. This can be information about the server software, what options the
service supports, a welcome message or anything else that the client can find
out before interacting with the server.

Shodan collects data mostly on web servers (HTTP/HTTPS – ports 80, 8080, 443, 8443),
as well as FTP (port 21), SSH (port 22), Telnet (port 23), SNMP (port 161), IMA
(ports 143, or (encrypted) 993), SMTP (port 25), SIP (port 5060), and Real Time
Streaming Protocol (RTSP, port 554). The latter can be used to access webcams and
their video streams.

### urlscan.io

[urlscan.io](https://urlscan.io) is a free service to scan and analyse websites.
When a URL is submitted to urlscan.io, an automated process will browse to the
URL like a regular user and record the activity that this page navigation creates.
This includes the domains and IPs contacted, the resources (JavaScript, CSS, etc)
requested from those domains, as well as additional information about the page itself.
urlscan.io will take a screenshot of the page, record the DOM content, JavaScript
global variables, cookies created by the page, and a myriad of other observations.
If the site is targeting the users one of the more than 900 brands tracked by urlscan.io,
it will be highlighted as potentially malicious in the scan results.

### Maltego

[Maltego](https://www.maltego.com) is a link analysis software used for
open-source intelligence, forensics and other investigations, originally
developed by Paterva from Pretoria, South Africa. Maltego offers real-time
data mining and information gathering, as well as the representation of this
information on a node-based graph, making patterns and multiple order
connections between said information easily identifiable.

### Recon-ng

The [Recon-ng Framework](https://github.com/lanmaster53/recon-ng) is an
Open Source Intelligence gathering tool aimed at reducing the time spent
harvesting information from open sources. Recon-ng is a full-featured
reconnaissance framework designed with the goal of providing a powerful
environment to conduct open source web-based reconnaissance quickly and thoroughly.

Recon-ng has a look and feel similar to the Metasploit Framework, reducing
the learning curve for leveraging the framework. However, it is quite different.
Recon-ng is not intended to compete with existing frameworks, as it is designed
exclusively for web-based open source reconnaissance. If you want to exploit,
use the Metasploit Framework. If you want to social engineer, use the
Social-Engineer Toolkit. If you want to conduct reconnaissance, use Recon-ng.

Recon-ng is a modular framework and makes it easy for Python developers to contribute.

### IntelOwl

[IntelOwl](https://github.com/intelowlproject/IntelOwl) is an Open Source
solution for management of Threat Intelligence at scale. It integrates a number
of analyzers available online and a lot of cutting-edge malware analysis tools.

It provides:

- Enrichment of Threat Intel for files as well as observables (IP, Domain, URL, hash, etc).
- A Fully-fledged REST API written in Django and Python.
- An easy way to be integrated in your stack of security tools to automate common jobs usually performed, for instance, by SOC analysts manually. (Thanks to the official libraries pyintelowl and go-intelowl)
- A built-in GUI: provides features such as dashboard, visualizations of analysis data, easy to use forms for requesting new analysis, etc.
- A framework composed of modular components called Plugins:
  - analyzers that can be run to either retrieve data from external sources (like VirusTotal or AbuseIPDB) or to generate intel from internally available tools (like Yara or Oletools)
  - connectors that can be run to export data to external platforms (like MISP or OpenCTI)
  - pivots that are designed to trigger the execution of a chain of analysis and connect them to each other
  - visualizers that are designed to create custom visualizations of analyzers results
  - ingestors that allows to automatically ingest stream of observables or files to IntelOwl itself
  - playbooks that are meant to make analysis easily repeatable

### DNS Twister

[DNS Twister](https://dnstwister.report) is anti-phishing domain name search
engine and DNS monitoring service.

### Online Cameras

[The Insecam project](http://www.insecam.org) is the world's largest directory
of online surveillance security cameras. Select a country to watch live street,
traffic, parking, office, road, beach, earth online webcams. Now you can search
live web cams around the world. You can find here Axis, Panasonic, Linksys, Sony,
TPLink, Foscam and a lot of other network video cams available online without
a password. The `Insecam project` takes several precautions to ensure individual
privacy is protected.


### IP Logger

[IP Logger](https://iplogger.org) is a URL Shortener with advanced analytics for
the traffic through your links, visitors on your online store, blog or website.
With IPLogger online services, you can find your own IP address, find location
of IP address, track the exact location of any mobile device or PC, and check
a URL for hidden redirects. There are several ways to collect detailed analytics
and track IP address: short links, an invisible pixel, a unique geo-logger tool
and URL tracker. You can use IP trap completely legally to collect user consent.

### People Search

[That's Them](https://thatsthem.com) helps you find people by using pieces of
information that you already know about someone. That's Them searches open source
records to find contact information on a person by name, street address, phone
number, email addresses, date of birth, business name, IP address, vehicle VIN
number or social network ID.

### ImgOps

[ImgOps](https://imgops.com) is an image operations meta-tool that combines all
the available image tools in one website. You can upload an image file or provide
a URL and you can use all the reverse image search engines available. `ImgOps`
can also extract metadata and provide other image information like geolocation.
There is a bookmarklet for convenience and you can also insert `https://imgops.com/`
in front of any image URL. 

## OSINT Kasm Workspace

An `OSINT` custom Kasm workspace is available. This workspace includes several
of the `OSINT` tools listed below. See https://github.com/doctorfree/kasm
