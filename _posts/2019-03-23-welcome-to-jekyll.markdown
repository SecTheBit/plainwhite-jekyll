---
layout: post
title:  "Access Control List in Active Directory"
date:   2020-04-01 21:03:36 +0530
categories: RedTeaming Pentest ActiveDirectory
---
Hello folks!!! hope you all are doing well , I am here to write a blog on the basics of *Active Directory* , and i hope you all like it. We will start with some definitions and then go to the Domain Enumeration part.

Active Directory is simply a Directory Service that was developed by Microsoft in the mid 1990s to replace the old Windows-NT style user authentication. It stores information about all the objects like computer, users, printers, shares , etc. you can think it as a phonebook for windows. It helps to manage all the objects under a domain in an efficient manner with the help of LDAP (Leight weight Directory Access Prototcol). Light Weight Directory Access Protocol is an application protocol for querying and modifying the Active Directory Services, will add more about LDAP in the next blog.


## *Components of the Active Directory*

1.*Domain Controller* 

Domain Controllers are the servers for the Active Directory which do all the essentials woorks like authentication , authorization , granting tickets , etc. For example , there are more than 1000 employee in an organization , so before going into the office everyone has to show their identity to the security officer , in the same way Domain Controller acts. The DC is configured to authorized or authenticate more computers in an organization.

2.*Domain*

A domain is a group of users, computers, printers, etc. in a network. Consider the below domain tree (hierarchy of domains) , in this image "abc.com" is the name of the domain (please consider half left part , will explain all later) , and "asia.abc.com" and "europe.abc.com" are two child domains of the root domain ("abc.com").

![Figure-1] (!https://github.com/SecTheBit/plainwhite-jekyll/blob/gh-pages/_posts/ad_forest_img1.jpg)

3.*Forest*



4.*Schema*

Schema is like a blue print, which describes the attributes or properties of the objects in the Active Directory Environment, whenerver you make changes in the schema it is replicated to all the domain controller in the entire forest, thus you have to be very carefull, otherwise it will lead to distortion of the entire forest. It is rare that you will manually make changes to the schema , some programs that are directly integrated with the Active Directory, like Microsoft Exchange, will make changes in the Schema for you. You should be very qualified to make changes to the schema and should also be a member of Active Directory Schema Admins to make changes in the schema.

4.



```javascript
const Razorpay = require('razorpay');

let rzp = Razorpay({
	key_id: 'KEY_ID',
	secret: 'name'
});

// capture request
rzp.capture(payment_id, cost)
	.then(function (data) {
		return 2;
	})
```

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
