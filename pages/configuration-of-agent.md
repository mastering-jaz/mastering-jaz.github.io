---
layout: default
title: Configuration of Job Agent
permalink: /configuration-of-agent/
redirect_from:
  - /configuration-of-agent.html
sitemap:
    priority: 0.7
    lastmod: 2016-06-24T00:00:00-00:00
---

# <i class="fa fa-keyboard-o"></i> Configuration of Job Agent

Since JAZ source is based on the Zabbix source, configuration files looks similar.

Following is the default job agent configuration file which comes with descriptive comments about each config parameter.

**Note: Those highlighted text explanations are not part of config file, their inclusions are just for providing information.**

**Note for Windows: Most settings are same. Directory value will be Windows-style.**

<p class="alert alert-info">Normally, you will need to set Server and Hostname. Rest works fine with default values. </p>


<pre>
# Job Arranger for ZABBIX
# This is a configuration file for Job Arranger Agent process

############ ZABBIX PARAMETERS INCLUDE #################

### Option: Include
#        You may include individual files or all files in a directory in the configuration file.
#
# Mandatory: no
# Default:
# Include=
<p class="alert alert-info">It is better to avoid use of `Include` as it better fits with Zabbix where you can have separate files for similar configuration.
<a href="http://serverfault.com/questions/795406">http://serverfault.com/questions/795406</a>
</p>

############ GENERAL PARAMETERS #################

### Option: TmpDir
#        Temporary directory.
#
# Mandatory: no
# Default:
# TmpDir=/tmp
TmpDir=/var/lib/jobarranger/tmp

### Option: Server
#        List of comma delimited IP addresses (or hostnames) of Zabbix servers.
#        Incoming connections will be accepted only from the hosts listed here.
#        No spaces allowed.
#        If IPv6 support is enabled then '127.0.0.1', '::127.0.0.1', '::ffff:127.0.0.1' are treated equally.
#
# Mandatory: no
# Default:
# Server=
Server=127.0.0.1
<p class="alert alert-info">Same as zabbix, provide job server ip/hostname.
Only single job server is allowed. Multiple server will not work.
</p>

### Option: Hostname
#        Unique, case sensitive hostname.
#        Required for active checks and must match hostname as configured on the server.
#
# Mandatory: no
# Default:
# Hostname=

<p class="alert alert-info">Same as zabbix, provide hostname as registered in Zabbix.</p>

############ ADVANCED PARAMETERS ################

### Option: AllowRoot
#        Allow the agent to run as 'root'. If disabled and the agent is started by 'root', the agent
#        will try to switch to user 'zabbix(Default)' instead. Has no effect if started under a regular user.
#        0 - do not allow
#        1 - allow
#
# Mandatory: no
# Default:
AllowRoot=0
<p class="alert alert-info">Allowing root access means you know what you are doing :P.</p>

### Option: ListenIP
#        List of comma delimited IP addresses that the agent should listen on.
#        First IP address is sent to Zabbix server if connecting to it to retrieve list of active checks.
#
# Mandatory: no
# Default:
# ListenIP=0.0.0.0

### Option: Timeout
#        Spend no more than Timeout seconds on processing
#
# Mandatory: no
# Range: 1-300
# Default: 5 (second)
# Timeout=5

### Option: DebugLevel
#        Specifies debug level
#        0 - no debug
#        1 - critical information
#        2 - error information
#        3 - warnings
#        4 - for debugging (produces lots of information)
#
# Mandatory: no
# Range: 0-4
# Default: 3
# DebugLevel=3
DebugLevel=3

### Option: LogFileSize
#        Maximum size of log file in MB.
#        0 - disable automatic log rotation.
#
# Mandatory: no
# Range: 0-1024
# Default: 1 (MB)
# LogFileSize=1
LogFileSize=1
<p class="alert alert-info">Set your desigred log size.</p>
############ JOB ARRANGER SPECIFIC PARAMETERS ################

### Option: JaLogFile
#        Name of log file.
#        If not set, syslog is used.
#
# Mandatory: no
# Default:
# JaLogFile=
JaLogFile=/var/log/jobarranger/jobarg_agentd.log

### Option: JaPidFile
#        Name of PID file.
#
# Mandatory: no
# Default:
# JaPidFile=/tmp/jobarg_agentd.pid
JaPidFile=/var/run/jobarranger/jobarg_agentd.pid

### Option: JaServerPort
#        Specify the listening port of the job server.
#
# Mandatory: no
# Range: 1024-32767
# Default: 10061
# JaServerPort=10061
JaServerPort=10061

### Option: JaListenPort
#        Agent will listen on this port for connections from the server.
#
# Mandatory: no
# Range: 1024-32767
# Default: 10055
# JaListenPort=10055
JaListenPort=10055

### Option: JaSendRetry
#        The number of times of a retry when a data transmitting error occurs.
#
# Mandatory: no
# Range: 0-3600
# Default: 30 (Number of times)
# JaSendRetry=30
JaSendRetry=30

### Option: JaDatabaseFile
#        The file name used by SQLite.
#
# Mandatory: yes
# Default:
# JaDatabaseFile=
JaDatabaseFile=/var/lib/jobarranger/jobarg_agentd.db

### Option: JaJobHistory
#        The period which saves job execution information at SQLite.
#        The retention period of job execution information is specified by a daily moving average.
#
# Mandatory: no
# Range: 1-365
# Default: 30 (Day)
# JaJobHistory=30
JaJobHistory=1

### Option: JaBackupTime
#        Backup implementation time of a SQLite database.
#        Specify the implementation time of the day.
#
# Mandatory: no
# Range: 1-24
# Default: 24 (Time)
# JaBackupTime=24
JaBackupTime=24

### Option: JaExtjobPath
#        Directory to place an extended job.
#
# Mandatory: yes
# Default:
# JaExtjobPath=
JaExtjobPath=/etc/jobarranger/extendedjob

### Option: JaFcopyTimeout
#        The communication timeout value at the time of a file transfer.
#
# Mandatory: no
# Range: 1-3600
# Default: 180 (second)
# JaFcopyTimeout=180

### Option: JaListenRetry
#        Specifies the number of retries if a listen error occurs.
#        Retry is performed every other second.
#
# Mandatory: no
# Range: 0-3600
# Default: 30 (Number of times)
# JaListenRetry=30

### Option: JaExecutionUser
#        Specify the execution user of job Arranger Agent.
#        This value is ignored in the windows version job agent.
#
# Mandatory: no
# Default: zabbix
# JaExecutionUser=zabbix

### Option: JaCommandUser
#        Specify the user to run the command.
#        You must set the "AllowRoot=1" option when using this option.
#
# Mandatory: no
# Default:
# JaCommandUser=

### Option: JaCommandPassword
#        Specify the password for Windows user run the command.
#        You must set the "AllowRoot=1" option when using this option.
#        This value is ignored in the Linux version job agent.
#
# Mandatory: no
# Default:
# JaCommandPassword=
</pre>