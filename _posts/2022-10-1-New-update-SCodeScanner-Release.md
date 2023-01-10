---
layout: post
title: ScodeScanner v3.1.0
---

ScodeScanner is an automated tool, created in purpose of finding the vulnerabilities inside the source code before commiting it into the production. This will help the developers to quickly identify the vulnerabilities and patch those vulnerabilities at Dev Time. 

### In Support Language

SCode Scanner now also supports YAML for kubernetes security misconfiguration. Upon finding any vulnerability, the SCodeScanner will generate results in JSON output file. SCodeScanner can scan complex RBAC Policies to find misconfigurations.

### New Improved Features?

1) Supported PHP Language
2) Supported YAML Language
3) Pass results to bug tracking services like Jira also Slack (Sending files to group to multiple people at once).
4) Gives results in JSON format, which can easily be used to any other program.
5) Works with Rules. We only need to create some rules which the target rule is not present in php/yaml directory.
6) Rules that can scan advance patterns


### How to run?

1) Download the repository

2) run pip install -r requirements.txt

3) python scscanner.py yaml --help

### Addional Information

* `--folder`: The flag takes the folder where the actual code resides. This is a required flag.

* `--file`: If we want to scan a file, the flag is required. 

* `--check`:  This flag will run the false remove after identifying the vulnerabilities. This basically checks whether the user input is real or not. The flag also creates a new modified JSON file after removing all the false positives. But the note point is, the tool will keep both original and modified versions of files.

* `--json`: Responsible for making the json files as output

* `-o`:  This flag will create a text file with the output findings. The purpose of this flag is to make a human readable file that is easy to read. The flag is optional.

* `--jira`: Responsible for sending output files to the JIRA instance. (Need to add configurations inside the config.json file.). The flag is optional.

* `--slack`:  Responsible for sending output files to SLACK instances. (Need to add configurations inside config.json file). The flag is optional.


### Download

SCodeScanner hosted with GitHub. Head to the <a href="https://github.com/agrawalsmart7/scodescanner">GitHub repository</a> for downloads, bug reports, and features requests.

### Contribution

Would love your thoughts on this, and would be great to work with community.

Thanks!
