---
layout: post
title:  "How to Test email template in SFDC Anonymous Window ? "
categories: Salesforce
tags:  email-template apex Salesforce
---
* content
{:toc}


## Question

How to Test email template in SFDC Anonymous Window ?






## Code

In normal case, we will use email Template to test our email in clicking 'Send Test and verify merge fields':

![alt tag](https://raw.githubusercontent.com/TonyRenHK/TonyRen/master/Img/B/2017-03-05-How-to-Testing-email-template-in-SFDC-Anonymous-Window1.JPG)

However, it sometimes, will have following result.

![alt tag](https://raw.githubusercontent.com/TonyRenHK/TonyRen/master/Img/B/2017-03-05-How-to-Testing-email-template-in-SFDC-Anonymous-Window2.JPG)

To testing email in Production env, we can use following code to test in Apex Anonymous Window.

```
Messaging.SingleEmailMessage mail =new Messaging.SingleEmailMessage(); 
 
//this set user Id 
mail.setTargetObjectId('005D0000008fQd4'); 
 
//This set Template Id 
mail.setTemplateId('00XD0000002J0Ma'); 
 
//this set record Id 
mail.setWhatId('a9ED00000000kNE');    
mail.setCCAddresses( new String[]{'tonyrenhk@outlook.com'}); 
mail.setBccSender(false); 
mail.setUseSignature(false); 
mail.setReplyTo('tony.ren@elufasys.com'); 
 
mail.setSenderDisplayName('Tony Testing in Production'); 
 
mail.setSaveAsActivity(false);  
Messaging.sendEmail(new Messaging.SingleEmailMessage[] { mail });

```
For how to use Apex Anonymous Window, you can perdorm with following path: Debug–>Open Execute Anonymous Window ( Ctrl+E).
Or view following post:
https://tonyrenhk.github.io/2016/11/10/How-to-log-issue-in-SFDC-by-sending-email/


Thanks for reading this article. Any code samples provided here are purely for experimental purposes. The primary purpose of this article is just to share the knowledge and my own experience. Nothing more, nothing less. Use this code and approach at your own risk.Please feel free to contact me (tonyrenhk@outlook.com) if you have any inquiry or the code have any problem. Thank you.
