---
layout: post
title:  "Spring 22 - Blog 1"
date:   2022-02-12.
categories: jekyll update
---

<h1> Create 5 test users using Azure Management Shell </h1>

In this blog, i will show how to connect to your Azure Active Directory and create some new users that will be used for testing.

**Note** If you prefer you can create the users in the UI using the 365 Admin centre via the users – active users management tool.

1.

Return to your windows powershell or open Windows PowerShell as Administrator type the following command and press enter.

**Note if you still have your previous Azure AD connection open in PowerShell you can skip to step 2.

a.

Import-Module MSOnline

b.

Connect-msolservice

c.

In the credential pop up box enter the following and then click OK

d.

Username = steve@CKXXXX.onmicrosoft.com where XXXX is your unique number – click next

e.

Password = Pa$$w0rd – click sign in.



2.

When you have been authenticated type the following and press enter

a.

Get-Msoluser

You should receive a return showing only Steve is in the tenant but is also licensed.



3.

In the command type the following and press enter. replace XXXX with your unique number

a.

New-MsolUser –UserPrincipalName pete@CKXXXX.onmicrosoft.com –DisplayName “Pete Coventry” –FirstName “Pete” –LastName “Coventry” –Password ‘Pa$$w0rd’ -ForceChangePassword $false –UsageLocation “GB”



4.

Repeat step 6 for the following users:

a.

Ashley Curtis

b.

Mark Summers

c.

Shannen Smith

d.

Tom Gooch

5.

Now run the following command to see the status of the users. Replace XXXX with your unique number.

a.

Get-Msoluser



Notice that the 5 new users are not licensed. Let’s add a license. You could also run get-msoluser -unlicenseduseronly if you just wanted a filtered view.

6.

To assign Pete a license type the following command. Replace XXXX with your unique number

a.

Set-MsolUserLicense -UserPrincipalName pete@CKXXXX.onmicrosoft.com –AddLicenses “CKXXXX:ENTERPRISEPREMIUM”

**Note** If you have used a different tenant type such as an E3 you will need to change the license type to match. For example: CKXXXX:

ENTERPRISEPACK. Use Get-MSOLAccountSKU to find out your license type.

7.

Repeat step 9 and add a license for Ashley, Mark, Tom and Shannen.

8.

Re-Run Get-Msoluser

You should now have all users licensed.

