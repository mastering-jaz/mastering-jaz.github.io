---
layout: default
title: Job Agent
permalink: /job-agent-concept/
redirect_from:
  - /job-agent-concept.html
sitemap:
    priority: 0.7
    lastmod: 2016-06-28T00:00:00-00:00
---

# <i class="fa fa-plug"></i> Job Agent

### Overview

Job agent is deployed and run as a daemon/service on each target host to instantly run the job upon receiving a job from Job Server.

It always listen on default port 10055 and as soon as it receives a job, it start executing the given job(mostly in a form of shell script).

Either job finished successfully or unsuccessfully, Job agent always send the result to Job server.

It uses SQLite to store and manage the jobs internally.

Job agents are extremely efficient because of using native [system calls](https://en.wikipedia.org/wiki/System_call).

### Agent process

Job agent runs as a daemon process. The agent can be started by executing:

```
shell>/usr/sbin/jobarg_agentd
```

You can use the following command line parameters with Job agent :

```
-c --config <file>   Absolute path to the configuration file
-h --help            Give this help
-V --version         Display version number
```

Examples of command line parameters:

```
shell>/usr/sbin/jobarg_agentd -c etc/jobarranger/jobarg_agentd.conf
shell>/usr/sbin/jobarg_agentd -h
shell>/usr/sbin/jobarg_agentd -V
```
**Process user**

Same as Zabbix agent, Job agent is designed to run as a non-root user.
However, if you want to run the process as root user then you have to change config `AllowRoot` parameter.
Rather than running the processes with root user, it is recommended to use a `sudo` user.

**Configuration file**

See the [configuration]({{ site.url }}/configuration-of-agent/) file options for details on configuring Job agent.

**Start-up scripts**

The scripts are used to automatically start/stop Job agent processes during system's start-up/shutdown.
The scripts are located under default directory for each platforms if you have installed from packages.

### Supported platforms
*   Redhat 5.x or later
*   CentOS 5.x or later
*   Windows Server 2003
*   Windows Server 2008 SP2 or later
*   Windows Server 2008 R2
*   HP-UX
*   IBM AIX
*   Amazon Linux - (starting from jaz version 3.2.x)

### Installation

See the [Installation]({{ site.url }}/install-job-agent-from-package/) section.