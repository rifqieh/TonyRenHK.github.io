---
layout: post
title:  "How to add 'Loading' Action Status when Searching in Salesforce?"
categories: Searching
tags:  Searching Apex
---
* content
{:toc}


## Question

How to add 'Loading' Action Status when Searching in Salesforce


## Solution

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
