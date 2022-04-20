---
layout: post
title: ScodeScanner v2.1.0
---

ScodeScanner is an automated tool, created in purpose of finding the vulnerabilities inside the source code before commiting it into the production. This will help the developers to quickly identify the vulnerabilities and patch those vulnerabilities at Dev Time. 

### In Support Language

ScodeScanner only supports PHP for now, but soon it will start supporting other languages too. 

### Whats new?

1) Added advance rules - It will detect if the variable is using user input validated function, and find the match accordingly.

  ```
  $var1 = $_GET['a'];
    $var2 = $_GET['b'];

   echo htmlspecialchars($var1 ); This will Ignore
   echo $var1; This will match

   $encryptedvalue = htmlspecialchars($var2);
   echo $encryptedvalue; this will ignore

   echo $var2; this will match

  ```
2) Added Jira Integration - Where you can directly send the file to Jira Instance

3) Added Slack Integration - Where you can send file to slack channel

4) Added --check flag - Which will double check the results 

  **Note**: This flag might miss the match where if one file imported variables from other file. So use accordingly.

5) Resolved Bugs

6) Edited Rules


### Download

SCodeScanner hosted with GitHub. Head to the <a href="https://github.com/agrawalsmart7/scodescanner">GitHub repository</a> for downloads, bug reports, and features requests.

### Contribution

Would love your thoughts on this, and would be great to work with community.

Thanks!
