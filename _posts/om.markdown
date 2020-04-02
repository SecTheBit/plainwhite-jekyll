---
layout: post
title:  "Testing"
date:   2020-04-01 21:03:36 +0530
categories: Pentesting
---
Hello folks!!! hope you all are doing well , I am here to write a blog on the basics of *Active Directory* , and i hope you all like it. We will start with some definitions and then go to the Domain Enumeration part.

Active Directory is simply a Directory Service that was developed by Microsoft in the mid 1990s to replace the old Windows-NT style user authentication. It stores information about all the objects like computer, users, printers, shares , etc. you can think it as a phonebook for windows. It helps to manage all the objects under a domain in an efficient manner with the help of LDAP (Leight weight Directory Access Prototcol). Light Weight Directory Access Protocol is an application protocol for querying and modifying the Active Directory Services, will add more about LDAP in the next blog.


## *Components of the Active Directory*

1.*Domain Controller* 

Domain Controllers are the servers for the Active Directory which do all the essentials woorks like authentication , authorization , granting tickets , etc. For example , there are more than 1000 employee in an organization , so before going into the office everyone has to show their identity to the security officer , in the same way Domain Controller acts. The DC is configured to authorized or authenticate more computers in an organization.

2.*Domain*

A domain is a group of users, computers, printers, etc. in a network. Consider the below domain tree (hierarchy of domains) , in this image "abc.com" is the name of the domain (please consider half left part , will explain all later) , and "asia.abc.com" and "europe.abc.com" are two child domains of the root domain ("abc.com").

![Figure-1](!https://github.com/SecTheBit/plainwhite-jekyll/blob/gh-pages/_posts/ad_forest_img1.jpg)

3.*Distinguished Names*:

Every object in the domain should be called using an unique path called as Distinguished Names. Like , in the figure 1, the Distinguished Name of the root node and a child node should be as follow:
dc=abc dc=com ; dc=asia dc=abc dc=com; ddc stands for domain component.
 
4.*Forest*

Forest is a collection of domain tree , which is a collection of domains. The first domain in the forest is called as the forest root domain , in the above figure the forest root domains are "abc.com" and "xyz.com" and all the other domains are their respective child domains.

5.*Schema*

Schema is like a blue print, which describes the attributes or properties of the objects in the Active Directory Environment, whenerver you make changes in the schema it is replicated to all the domain controller in the entire forest, thus you have to be very carefull, otherwise it will lead to distortion of the entire forest. It is rare that you will manually make changes to the schema , some programs that are directly integrated with the Active Directory, like Microsoft Exchange, will make changes in the Schema for you. You should be very qualified to make changes to the schema and should also be a member of Active Directory Schema Admins to make changes in the schema.

6*Trust*

Trust establishes a connection ,for the users, between the domains for accessing the resources present in other domains.Trust are of two types:

a. Directional : The trust flows from the trusting domain to trusted domain, trusted domain should have the right to access the resource of the trusting domain. There are other two types of trust on the basis of direction:

i.  One-Way Trust: Only one domain is allowed to access the resource.
ii. Bi-Directional: Both the domains can access the resource of each other.

b. Transitive: The trust relationship is extended beyond a two-domain trust to include other trusted domains. For example: if the domain "A" trust the domain "B" and the domain "B" trust the domain "C" , then in that case , domain "A" will automatically trust the domain "C".



