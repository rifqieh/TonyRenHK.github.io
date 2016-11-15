---
layout: post
title:  "How to add 'Loading' Action Status when Searching in Salesforce?"
categories: Searching
tags:  Searching Apex
---
* content
{:toc}

## Question

How to add 'Loading' Action Status when Searching in Salesforce?






## Demo


How to add'Loading' when searching?
The following code can be added in Visualforce page.
javascript code:

```
$(document).on('mousemove', function(e){
            $('#loadtext').css({
               left:  e.pageX,
               top:   e.pageY
            });
        });
```

Apex Code in salesforce:



Searching Button:

```
<apex:commandButton value="<<" action="{!firstPage}" reRender="results,debug,error,pagination" status="ActionStatus" />
```

The Final result like this:




Any code samples provided here are purely for experimental purposes and comes with no warranty or support.  The primary purpose of this article is just to share the knowledge and my own experience. Nothing more, nothing less. Use this code and approach at your own risk.Please feel free to contact me (yamshingkwan@gmail.com) if you have any inquiry or the code have any problem. Thank you.

