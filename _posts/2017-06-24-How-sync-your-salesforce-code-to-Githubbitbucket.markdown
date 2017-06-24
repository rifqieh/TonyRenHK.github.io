---
layout: post
title:  "How sync your salesforce code to Github/bitbucket?"
categories: Salesforce
tags:  Salesforce Apex bitbucket
---
* content
{:toc}

## Question

[Code version Management/Control]How sync your salesforce code to Github/bitbucket?





## Situation

Version control, for most developers, is an absolute must in any professional setting. However, currently, in salesforce org, there dont have Code version Management/Control. 
One solution is using plug-in(Subversion) for Eclipse, but it need the deveploer to install Eclipse in their local machine.




## Solution


Today, I will introduce one solution which is using unix+ nodejs to retrieve salesforce code and then push the code to Githut/Bitbucket.



**Method**


Firstly, I will setup my linux workspace, there, I use cloud9. Also, you can use your local machine.

Secondly, I will retrieve all code-related metadata in salesforce, this include lightning component, apex Component/Visual force page, class. and tigger .

Thirdly, I will push all related code to the Githut/Bitbucket.

All above steps will be like following.

![alt tag](https://raw.githubusercontent.com/TonyRenHK/Demo/master/Blog/2017-06-24-How-sync-your-salesforce-code-to-Githubbitbucket.png)




**retrieve all Code-Related Metadata**



There, I use JSForce library to retrieve all Code-Related Metadata and object matadata.
Also you need to install related library in your machine

* npm install jsforce
* npm install js-beautify
* npm install mkdirp



The related code:

{% include GistCode.html id="f4d3ed2a3a4ce3a22c256d224ad739bd" %}



**Cloning Repository and push the code to the Repository using shell script**





Firstly, I create shell script file named 'Gitshell.sh', I the shell script file, I will do following things:

* create one foler name 'backup'.
* Clone my Repository from Githut/Bitbucket in 'backup' foler.
* Retrieve salesforce code from Sandbox/Production using nodejs JSForce.
* Move the Retrieved code to the cloned Repository folder.
* Push all related the changes to Githut/Bitbucket.

The related code:

{% include GistCode.html id="f104481b045fde58e767c029b077a662" %}


You can run 'bash Gitshell.sh' Linux Terminal





Any code samples provided here are purely for experimental purposes and comes with no warranty or support.  The primary purpose of this article is just to share the knowledge and my own experience. Nothing more, nothing less. Use this code and approach at your own risk.Please feel free to contact me (yamshingkwan@gmail.com) if you have any inquiry or the code have any problem. Thank you.

