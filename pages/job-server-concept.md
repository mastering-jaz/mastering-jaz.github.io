---
layout: default
title: Job Server
permalink: /job-server-concept/
redirect_from:
  - /job-server-concept.html
sitemap:
    priority: 0.7
    lastmod: 2016-06-28T00:00:00-00:00
---

# <i class="fa fa-plug"></i> Job Server

### Overview

Job server is the central process of JAZ software.

The server performs checking calendars and schedules. 
Based on that information, it start JobNets, execute the whole JobNet by executing each icon according to flow.
It receives agent sent data about job execution results. It also process external program requests such as for <code>jobarg_exec</code>.

You can also run an agentless job which is handled directly by Job Server.

It check Zabbix for hosts, user information, etc during a job execution or as necessary.

### Server process

Job server runs as a daemon process. The server can be started by executing:

```
shell>/usr/sbin/jobarg_server
```

You can use the following command line parameters with Job server :

```
-c --config <file>   Absolute path to the configuration file
-h --help            Give this help
-V --version         Display version number
```

Examples of command line parameters:

```
shell>/usr/sbin/jobarg_server -c etc/jobarranger/jobarg_server.conf
shell>/usr/sbin/jobarg_server -h
shell>/usr/sbin/jobarg_server -V
```
**Process user**

Same as Zabbix server, Job server is designed to run as a non-root user. 
However, if you want to run the process as root user then you have to change config `AllowRoot` parameter.

**Configuration file**

See the [configuration]({{ site.url }}/#) file options for details on configuring Job Server.

**Start-up scripts**

The scripts are used to automatically start/stop Job Server processes during system's start-up/shutdown.
The scripts are located under default directory for each platforms if you have installed from packages.

### Supported platforms
*   Redhat 5.x or later

*   CentOS 5.x or later

**With version 3.0.0 realease, it seems they have dropped job server release for Redhat/CentOS 5.x**