---
layout: post
title:  "Blog 3 - Security"
date:   2021-10-8
categories: jekyll update
---

<h1> Groups </h1>

The following groups are used to organize users in both Azure and SharePoint...

- Distribution Group: A group that is used only for e-mail distribution. You cannot add distribution groups to SharePoint groups, but you can expand a distribution group and add the individual members to a SharePoint group.


- Security Group: A security group that can be used to control permissions. You can use security groups to control permissions for your site by adding security groups to SharePoint groups and granting permissions to the SharePoint groups.

<h2> Access </h2>

Adding security groups to SharePoint groups provides centralized management of groups and security. The security group is the only place where you manage individual users. Once you add the security group to a SharePoint group, you do not have to manage security group members in that SharePoint group. If a user is removed from the security group, the user will be automatically removed from the SharePoint group.

Each organization sets up its security groups differently. For easier permission management, security groups should be large and stable enough that you are not continually adding more security groups to your SharePoint sites. If the project is small enough, you can assign individual permissions.

For example, we named a security group "Accounting - Rep" and it is not small enough to assign individual permissions, unless all users in "Accounting - Rep" have the same job function, such as reviewing checks. Therefore, we have to create a security group after the name, and only that group will view the specifics of their job function, no one else can see. Permissions control access to sites and site content. Fine-grained permissions also help to secure content at the item and document level.

<img src=" https://docs.microsoft.com/en-us/sharepoint/sharepointonline/media/manage-security-groups.png" 