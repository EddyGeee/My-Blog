---
layout: post
title:  "Blog 8 - ipconfig  "
date:   2021-11-05.
categories: jekyll update
---



A windows command line utility that is used to manage the IP address assigned to the machine it is running in. Used without any additional parameters, it displays the computer's currently assigned IP, subnet mask and default gateway addresses. IPCONFIG has several command line switches (parameters) preceded with a slash. 

Displays all current TCP/IP network configuration values and refreshes Dynamic Host Configuration Protocol (DHCP) and Domain Name System (DNS) settings. Used without parameters, ipconfig displays Internet Protocol version 4 (IPv4) and IPv6 addresses, subnet mask, and default gateway for all adapters.

Every device that connects to the Internet has its own Internet Protocol (IP) address. IP addresses make it possible, among other things, for computers from different networks to find each other. IP addresses are vital for all Internet-based activities, and yet it's not uncommon that a user doesn't know his computer's IP address or what it's good for.

<h2> Syntax </h2>

* `ipconfig` display the basic network configuration for all adapters
* `ipconfig /all` displays the full current network configurations for all adapters 
* `ipconfig /renew Local Area Connection` renews a DHCP-assigned IP address configuration for only the Local Area Connection adapter
* `ipconfig /displaydns` displays the contents of the DNS client resolver cache


These commands are most useful on computers that are configured to obtain an IP address automatically. This enables users to determine which TCP/IP configuration values have been configured by DHCP, Automatic Private IP Addressing (APIPA), or an alternate configuration. 




