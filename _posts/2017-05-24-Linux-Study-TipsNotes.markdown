---
layout: post
title:  "Linux Study Tips/Notes"
categories: Linux
tags:  Linux Notes
---
* content
{:toc}

## Question

Linux Study Tips/Notes






## Solution

I use Cloud 9 Linux workspace and following notes will be useful in linux env.

#### Zipping and Unzipping Files under Linux

install :
```
$ sudo apt-get install zip unzip
```

Unzip File
```
$ unzip data.zip
```

Adding Password: only for direct folder



```
zip --encrypt secure.zip * 
 
zip --encrypt secure.zip file 

```

This is more insecure, as the password is entered/shown as plain text: 

```
zip --password (password) file.zip files 
```

How To Archive All Files And Sub Folders In A Zip File 


```
zip -r *
```

#### How To Archive All Files And Sub Folders In A Zip File with password

```
zip -r --encrypt secure.zip *
```


Use the following command to uncompress a ZIP file: 

```
$ unzip secure.zip 
 
Enter password: 
*** 
```  
  

#### How to download a file from a website via terminal?  

```
$ wget "https://github.com/github/git-lfs/releases/download/v1.1.0/git-lfs-linux-amd64-1.1.0.tar.gz" 
 
 ```
 
 
Reference Link : 
https://www.cyberciti.biz/tips/how-can-i-zipping-and-unzipping-files-under-linux.html 
 
https://www.lifewire.com/practical-examples-of-the-zip-command-2201158 


https://www.shellhacks.com/create-password-protected-zip-file-linux/ 


Any code samples provided here are purely for experimental purposes and comes with no warranty or support.  The primary purpose of this article is just to share the knowledge and my own experience. Nothing more, nothing less. Use this code and approach at your own risk.Please feel free to contact me (yamshingkwan@gmail.com) if you have any inquiry or the code have any problem. Thank you.
