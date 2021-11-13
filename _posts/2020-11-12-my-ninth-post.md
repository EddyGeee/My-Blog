---
layout: post
title:  "Blog 8 - ipconfig  "
date:   2021-11-05.
categories: jekyll update
---

<h1> ipconfig </h1> 

Displays all current TCP/IP network configuration values and refreshes Dynamic Host Configuration Protocol (DHCP) and Domain Name System (DNS) settings. Used without parameters, ipconfig displays Internet Protocol version 4 (IPv4) and IPv6 addresses, subnet mask, and default gateway for all adapters.

<h2> Syntax </h2>

* `ipconfig` display the basic network configuration for all adapters
* `ipconfig /all` displays the full current network configurations for all adapters 
* `ipconfig /renew Local Area Connection` renews a DHCP-assigned IP address configuration for only the Local Area Connection adapter
* `ipconfig /displaydns` displays the contents of the DNS client resolver cache


These commands are most useful on computers that are configured to obtain an IP address automatically. This enables users to determine which TCP/IP configuration values have been configured by DHCP, Automatic Private IP Addressing (APIPA), or an alternate configuration. 




