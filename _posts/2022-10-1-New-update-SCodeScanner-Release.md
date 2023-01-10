---
layout: post
title: ScodeScanner v3.1.0
---

ScodeScanner is an automated tool, created in purpose of finding the vulnerabilities inside the source code before commiting it into the production. This will help the developers to quickly identify the vulnerabilities and patch those vulnerabilities at Dev Time. 

### In Support Language

SCode Scanner now also supports YAML for kubernetes security misconfiguration. Upon finding any vulnerability, the SCodeScanner will generate results in JSON output file. SCodeScanner can scan complex RBAC Policies to find misconfigurations.

### Whats new?

1) Added advance rules - 

2) Added Jira Integration - Where you can directly send the file to Jira Instance

3) Added Slack Integration - Where you can send file to slack channel

4) Added --check flag - Which will double check the results 

### How to run?

1) Download the repository
2) run pip install -r requirements.txt
3) python scscanner.py yaml --help

### Download

SCodeScanner hosted with GitHub. Head to the <a href="https://github.com/agrawalsmart7/scodescanner">GitHub repository</a> for downloads, bug reports, and features requests.

### Contribution

Would love your thoughts on this, and would be great to work with community.

Thanks!
