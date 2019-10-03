# HoundSploitBash.  An advanced command-line search engine for Exploit-DB


Author: Nicolas Carolo <nicolascarolo.dev@gmail.com>

Copyright: © 2019, Nicolas Carolo.

Date: 2019-10-03

Version: 1.5.0


## PURPOSE

HoundSploit Bash is an advanced command-line search engine for Exploit-DB developed in Python, born with the
aim of showing the user the most accurate search results.

### Features

* Effective version number filtering
* Open the source code of exploits and shellcodes using _nano_
* View information about the characteristics of exploits and shellcodes
* Automatic check for updates

#### Effective version number filtering examples
##### Example I

```
nicolas@carolo:~$ searchsploit WordPress 2.0.2
WordPress 2.0.2- 'cache' Remote Shell Injection
WordPress Plugin Crawl Rate Tracker 2.0.2 - SQL Inject
WordPress Plugin Sodahead Polls 2.0.2 - Multiple Cross
```

```
nicolas@carolo:~$ HoundSploitBash "wordpress 2.0.2"
10 exploits and 0 shellcodes found.

EXPLOITS:
+-------+---------------------------------------------------------------------------------------+
|    ID | DESCRIPTION                                                                           |
+=======+=======================================================================================+
|     6 | WordPress 2.0.2 - 'cache' Remote Shell Injection                                      |
+-------+---------------------------------------------------------------------------------------+
|  4397 | WordPress 1.5.1.1 < 2.2.2 - Multiple Vulnerabilities                                  |
+-------+---------------------------------------------------------------------------------------+
| 10088 | WordPress 2.0 < 2.7.1 - 'admin.php' Module Configuration Security Bypass              |
+-------+---------------------------------------------------------------------------------------+
| 10089 | WordPress < 2.8.5 - Unrestricted Arbitrary File Upload / Arbitrary PHP Code Execution |
+-------+---------------------------------------------------------------------------------------+
| 17755 | WordPress Plugin Crawl Rate Tracker 2.0.2 - SQL Injection                             |
+-------+---------------------------------------------------------------------------------------+
| 29754 | WordPress < 2.1.2 - 'PHP_Self' Cross-Site Scripting                                   |
+-------+---------------------------------------------------------------------------------------+
| 35414 | WordPress < 4.0.1 - Denial of Service                                                 |
+-------+---------------------------------------------------------------------------------------+
| 35475 | WordPress Plugin Sodahead Polls 2.0.2 - Multiple Cross-Site Scripting Vulnerabilities |
+-------+---------------------------------------------------------------------------------------+
| 41497 | WordPress < 4.7.1 - Username Enumeration                                              |
+-------+---------------------------------------------------------------------------------------+
| 41963 | WordPress < 4.7.4 - Unauthorized Password Reset                                       |
+-------+---------------------------------------------------------------------------------------+
```


##### Example II

```
nicolas@carolo:~$ searchsploit Linux Kernel 4.2.3
Exploits: No Result
Shellcodes: No Result
Papers: No Result
```

```
nicolas@carolo:~$ HoundSploitBash "linux kernel 4.2.3"
14 exploits and 0 shellcodes found.

EXPLOITS:
+-------+-------------------------------------------------------------------------------------------------------+
|    ID | DESCRIPTION                                                                                           |
+=======+=======================================================================================================+
| 41995 | Linux Kernel 3.11 < 4.8 0 - 'SO_SNDBUFFORCE' / 'SO_RCVBUFFORCE' Local Privilege Escalation            |
+-------+-------------------------------------------------------------------------------------------------------+
| 42136 | Linux Kernel < 4.10.13 - 'keyctl_set_reqkey_keyring' Local Denial of Service                          |
+-------+-------------------------------------------------------------------------------------------------------+
| 42762 | Linux Kernel < 4.13.1 - BlueTooth Buffer Overflow (PoC)                                               |
+-------+-------------------------------------------------------------------------------------------------------+
| 42932 | Linux Kernel < 4.14.rc3 - Local Denial of Service                                                     |
+-------+-------------------------------------------------------------------------------------------------------+
| 43345 | Linux kernel < 4.10.15 - Race Condition Privilege Escalation                                          |
+-------+-------------------------------------------------------------------------------------------------------+
| 43418 | Linux Kernel < 4.4.0-83 / < 4.8.0-58 (Ubuntu 14.04/16.04) - Local Privilege Escalation (KASLR / SMEP) |
+-------+-------------------------------------------------------------------------------------------------------+
| 44298 | Linux Kernel < 4.4.0-116 (Ubuntu 16.04.4) - Local Privilege Escalation                                |
+-------+-------------------------------------------------------------------------------------------------------+
| 44300 | Linux Kernel < 4.4.0-21 (Ubuntu 16.04 x64) - 'netfilter target_offset' Local Privilege Escalation     |
+-------+-------------------------------------------------------------------------------------------------------+
| 44301 | Linux Kernel < 4.5.1 - Off-By-One (PoC)                                                               |
+-------+-------------------------------------------------------------------------------------------------------+
| 44325 | Linux Kernel < 4.15.4 - 'show_floppy' KASLR Address Leak                                              |
+-------+-------------------------------------------------------------------------------------------------------+
| 44579 | Linux Kernel < 4.17-rc1 - 'AF_LLC' Double Free                                                        |
+-------+-------------------------------------------------------------------------------------------------------+
| 44832 | Linux Kernel < 4.16.11 - 'ext4_read_inline_data()' Memory Corruption                                  |
+-------+-------------------------------------------------------------------------------------------------------+
| 45010 | Linux Kernel < 4.13.9 (Ubuntu 16.04 / Fedora 27) - Local Privilege Escalation                         |
+-------+-------------------------------------------------------------------------------------------------------+
| 45553 | Linux Kernel < 4.11.8 - 'mq_notify: double sock_put()' Local Privilege Escalation                     |
+-------+-------------------------------------------------------------------------------------------------------+
```

## MINIMUM REQUIREMENTS

### Supported OS

* Linux
* macOS

### Interpreter and tools

* Python 3
* SQLite 3
* nano
* wget

## INSTALLATION

We can install HoundSploitBash simply by doing:
```sh
git clone https://github.com/nicolas-carolo/HoundSploitBash
cd HoundSploitBash
pip install -r requirements.txt
python setup.py install
```

## USAGE

| ACTION                                             | COMMAND LINE                                     |
|----------------------------------------------------|--------------------------------------------------|
| Perform a search                                   | HoundSploitBash "[search text]"                  |
| Perform a search (without keywords highlighting)   | HoundSploitBash --nokeywords "[search text]"     |
| Perform a search (no table for results)            | HoundSploitBash --notable "[search text]"        |
| Show info about the exploit                        | HoundSploitBash -ie [exploit's id]               |
| Show info about the shellcode                      | HoundSploitBash -is [shellcode's id]             |
| Open the exploit's source code with nano           | HoundSploitBash -oe [exploit's id]               |
| Open the shellcode's source code with nano         | HoundSploitBash -os [shellcode's id]             |
| Show software information                          | HoundSploitBash -v                               |
| Show help                                          | HoundSploitBash -help                            |
| Check for software updates                         | HoundSploitBash -u                               |
| Check for database updates                         | HoundSploitBash -udb                             |


## COPYRIGHT

Copyright © 2019, Nicolas Carolo.
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

1. Redistributions of source code must retain the above copyright
   notice, this list of conditions, and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions, and the following disclaimer in the
   documentation and/or other materials provided with the distribution.

3. Neither the name of the author of this software nor the names of
   contributors to this software may be used to endorse or promote
   products derived from this software without specific prior written
   consent.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
