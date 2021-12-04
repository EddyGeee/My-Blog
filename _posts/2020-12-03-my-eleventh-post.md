---
layout: post
title:  "Blog 10 - TLS Certificates "
date:   2021-12-03.
categories: jekyll update
---
<h1> What is TLS? </h1>

Transport Layer Security is a protocol that establishes an encrypted session between two computers on the Internet. It verifies the identity of the server and prevents hackers from intercepting any data.

Whenever you send or receive information on the Internet, it passes through a network of multiple computers to reach the destination. Historically, any of these computers could read your data, because it was not encrypted.

<h2> What is a TLS Certificate? </h2> 

Digital certificates, also known as identity certificates or public key certificates, are digital files that are used to certify the ownership of a public key. TLS certificates are a type of digital certificate, issued by a Certificate Authority (CA). The CA signs the certificate, certifying that they have verified that it belongs to the owners of the domain name which is the subject of the certificate.

TLS certificates usually contain the following information:

The subject domain name
The subject organization
The name of the issuing CA
Additional or alternative subject domain names, including subdomains, if any
Issue date
Expiry date
The public key (The private key, however, is a secret.)
The digital signature by the CA


