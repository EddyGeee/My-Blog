---
layout: post
title:  "Spring 22 - Blog 4"
date:   2022-03-12.
categories: jekyll update
---

This week I assisted my friend in uploading an SSL certificate for his REST API to enable secure and encrypted connection within his application. I won't be going through the whole architecture of the application but I'll share the steps I took to enabling HTTPS connection between his front-end application and his backend services. 

With the ever-expanding Internet, the need for privacy is at an all time high. Companies are constantly hiring networking specialists and system administrators to help in increasing the security of their application. One of those tasks is uploading and managing an SSL/TLS certificate on an application or website. 

The first step I took was checking to see if a proper domain was attached to the site for simplicity purposes. In the scenario I was in I recommended my friend [freenom.com][free-nom] as they provide a wide array of free public domains. 

Next, I had to choose which SSL/TLS provider I wanted to use and if a wildcard certificate was necessary. I highly recommend using [Let's Encrypt][let-encrypt] for free SSL/TLS certificates as it's their goal to encrypt everything on the internet. They are otherwise known as a free CA (certificate authority) an issuer of digital certificates that certifies the ownership of the public key with the subject of the certificate. 

You will soon be redirected to [Certbot][cert-bot] a bot specializing in the automation of uploading certificates onto your servers. Simply choose which web server your website/api is running on (Apache, NGINX, etc) and OS then you'll be prompted with a set of instructions to get your certificates uploaded. In my case, I had an Amazon Linux 2 EC2 instance running on an Apache web server.

![Imgur](https://i.imgur.com/NR3m6AH.png?1)

I recommend running the command that allows Cerbot to edit your Apache config file automatically to save time, but for those who prefer to configure themselves do the manual approach. Once my domain was served I had to configure Apache as a reverse proxy to then enable communication between the API and the hosted frontend application.

**Notes**

I considered using [Amazon Certificate Manager][ACM] due to some of the application services living on AWS but for the sake of time Let's Encrypt was the best option.

Some alternatives to enabling HTTPS connection would be using hosting services that will provide it for you (Netlify, WordPress, FireBase, etc) but it's always good to learn how to do it on your own and adding it to your skill set.

Thanks for reading! 

[let-encrypt]: https://letsencrypt.org/ 
[cert-bot]: https://certbot.eff.org/ 
[ACM]: https://aws.amazon.com/certificate-manager/ 
[free-nom]: https://www.freenom.com/en/freeandpaiddomains.html