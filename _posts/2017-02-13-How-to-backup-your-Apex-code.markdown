---
layout: post
title:  "[JSForce] How to backup your Apex code/metadata in Salesforce? "
categories: Salesforce
tags:  backup apex Salesforce metadata
---
* content
{:toc}


## Question

[JSForce tutorial]: How to backup your Apex code/metadata in your Salesforce organization in your Local Side






## Background



As you know, salesforce currently, don’t have code version management, and developers should backup and manage code in their local side for their future comparison. Today, I will share some experience about how we backup our Apex code/metadata in our local side. 
 
 
The library we are used is JSFORCE (https://jsforce.github.io/document/#bulk-api)  and you need to finish related setup in your side 
 
And I used one JavaScript library named 'js-beautify' (https://www.npmjs.com/package/js-beautify) which can reformat the metadata in our local file.


##  How to use Jsforce to login SFDC Production env?

I run following code in CLOUD9 and I will connect to Production ENV. 
 

```
var jsforce = require('jsforce'); 
var conn = new jsforce.Connection({ 
    loginUrl: 'https://login.salesforce.com',//'https://login.salesforce.com', 
    version: '36.0' 
}); 
 
conn.login('YOURACCOUNT', 'YOURASSWORD', function(err, res) { 
    if (err) { 
        return console.error(err); 
    } 
   console.log('OK'); 
});

```
In normal case, we will have following error: 
 
```
tonyrenhk:~/workspace $ node PD1209.js 
[Error: LOGIN_MUST_USE_SECURITY_TOKEN: Invalid username, password, security token; or user locked out. Are you at a new location? When accessing Salesforce--either via a desktop client or the API--from outside of your company’s trusted networks, you must add a security token to your password to log in. To get your new security token, log in to Salesforce. From your personal settings, enter Reset My Security Token in the Quick Find box, then select Reset My Security Token.] 
tonyrenhk:~/workspace $ node PD1209.js 
OK
``` 
 

Are you including your Security Token with your password? Unless your org is configured to allow login without a security token, you will need to include it in the password field of your connection request. So your password entry will be 'passwordXXXXXX', where 'XXXXXX' is your security token. 
If you don't know your security token, follow the instructions in the error message to reset it. 
 
 
## MeataData Backup

The following Code should be run in Nodejs server to backup metadata: 

{% include GistCode.html id="f69d3f9ad26fac9e777a4f429ec27354" %}


## Apex Code Backup 
 
 
I will backup all of Apex Class/Apex Page and Visualforce Components in one time. Please be noted that the function can only query 200 record in one time. 
 
 
### Code:  

{% include GistCode.html id="2315fcb589e53872a7752ff4d3e10956" %}



If you think there’s a better way of doing this, please do share. 

Thanks for reading this article. Any code samples provided here are purely for experimental purposes. The primary purpose of this article is just to share the knowledge and my own experience. Nothing more, nothing less. Use this code and approach at your own risk.Please feel free to contact me (tonyrenhk@outlook.com) if you have any inquiry or the code have any problem. Thank you.
