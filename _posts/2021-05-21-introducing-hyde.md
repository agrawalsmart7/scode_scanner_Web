---
layout: post
title: Introducing ScodeScanner
---

ScodeScanner is an automated tool, created in purpose of finding the vulnerabilities inside the source code before commiting it into the production. This will help the developers to quickly identify the vulnerabilities and patch those vulnerabilities at Dev Time. 

### In Support Language

ScodeScanner only supports PHP for now, but soon it will start supporting other languages too. 

### SCodeScanner features

Features are:-

* Support for scanning the folder which contains multiple PHP files. 
* This will not only notify at which file but also notify you at which line the vulnerable code exists for quickly identifying the vulnerability.
* This scans not only the PRE-Defined PHP variables but also scans the custom variables. Like a `$test1 = $_GET["aaa"].` then it scans for both $test1 and the GET variables inside the source code.
* It scans functions with a function that contains our variable. Like `include(htmlentities($test))` so it will parse this and give the results like the $test variable found inside the include function. Because there might be possiblity of using base64 function instead of htmlentities.
* Support of parsing the whitespacese
* Output results in PHP file which contains HTML anchor tags (for browsing smoothly).
* It runs on your localhost, where you will have to give the folder name for scans.
* You can add more functions which are dangerous if you found missing any inside the vulnerablefunctions python file. 


### Download

SCodeScanner hosted with GitHub. Head to the <a href="https://github.com/agrawalsmart7/scodescanner">GitHub repository</a> for downloads, bug reports, and features requests.

### Contribution

Would love your thoughts on this, and would be great to work with community.

Thanks!
