---
layout: default
title: Configuration of Job Server
permalink: /configuration-of-server/
redirect_from:
  - /configuration-of-server.html
sitemap:
    priority: 0.7
    lastmod: 2016-06-24T00:00:00-00:00
---

# <i class="fa fa-keyboard-o"></i> Configuration of Job Server

Since JAZ source is based on the Zabbix source, configuration files looks similar.

Following is the default job server configuration file which comes with descriptive comments about each config parameter.

**Note: Those highlighted text explanations are not part of config file, their inclusions are just for providing information.**


<p class="alert alert-info">Normally, you will need to set Database user/password. Rest works fine with default values. </p>


<pre>
# Job Arranger for ZABBIX
# This is a configuration file for Job Arranger Server process

############ ZABBIX PARAMETERS INCLUDE #################

### Option: Include
#        You may include individual files or all files in a directory in the configuration file.
#
# Mandatory: no
# Default:
# Include=
<p class="alert alert-info">It is better to avoid use of `Include` as it better fits with Zabbix where you can have separate files for similar configuration.
<a href="http://serverfault.com/questions/795406" target="blank">http://serverfault.com/questions/795406</a>
</p>
############ GENERAL PARAMETERS #################

### Option: TmpDir
#        Temporary directory.
#
# Mandatory: no
# Default:
# TmpDir=/tmp
TmpDir=/var/lib/jobarranger/tmp

### Option: DBHost
#        Database host name.
#        If set to localhost, socket is used for MySQL.
#        If set to empty string, socket is used for PostgreSQL.
#
# Mandatory: no
# Default:
# DBHost=localhost

### Option: DBName
#        Database name.
#        For SQLite3 path to database file must be provided. DBUser and DBPassword are ignored.
#
# Mandatory: yes
# Default:
# DBName=
DBName=

### Option: DBSchema
#        Schema name. Used for IBM DB2.
#
# Mandatory: no
# Default:
# DBSchema=

### Option: DBUser
#        Database user. Ignored for SQLite.
#
# Mandatory: yes
# Default:
# DBUser=
DBUser=

### Option: DBPassword
#        Database password. Ignored for SQLite.
#        Comment this line if no password is used.
#
# Mandatory: no
# Default:
# DBPassword=
DBPassword=

### Option: DBSocket
#        Path to MySQL socket.
#
# Mandatory: no
# Default:
# DBSocket=/tmp/mysql.sock

### Option: DBPort
#        Database port when not using local socket. Ignored for SQLite.
#
# Mandatory: no
# Range: 1024-65535
# Default: 3306 (for MySQL)
# DBPort=3306

############ ADVANCED PARAMETERS ################

### Option: LogSlowQueries
#        How long a database query may take before being logged (in milli seconds)
#        0 - don't log slow queries.
#
# Mandatory: no
# Range: 0-3600000
# Default: 0
# LogSlowQueries=0

### Option: ListenIP
#        Trapper will listen on all network interfaces if this parameter is missing.
#
# Mandatory: no
# Default:
# ListenIP=0.0.0.0

### Option: SourceIP
#        Source IP address for outgoing connections.
#
# Mandatory: no
# Default:
# SourceIP=

### Option: Timeout
#        Specifies how long we wait for job agent check.
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
<p class="alert alert-info">Set your desigred log size</p>
############ JOB ARRANGER SPECIFIC PARAMETERS ################

### Option: JaLogFile
#        Name of Job Arranger log file.
#        If not set, syslog is used.
#
# Mandatory: no
# Default:
# JaLogFile=
JaLogFile=/var/log/jobarranger/jobarg_server.log

### Option: JaPidFile
#        Name of PID file.
#
# Mandatory: no
# Default:
# JaPidFile=/tmp/jobarg_server.pid
JaPidFile=/var/run/jobarranger/jobarg_server.pid

### Option: JaSelfmonInterval
#        Jaselfmon Execution interval.
#
# Mandatory: no
# Default: 1 (second)
# JaSelfmonInterval=1

### Option: JaLoaderInterval
#        Jaloaer Execution interval.
#
# Mandatory: no
# Default: 30 (second)
# JaLoaderInterval=30

### Option: JaBootInterval
#        Jaboot Execution interval.
#
# Mandatory: no
# Default: 1 (second)
# JaBootInterval=1

### Option: JaJobnetInterval
#        Jajobnet Execution interval.
#
# Mandatory: no
# Default: 1 (second)
# JaJobnetInterval=1

### Option: JaJobInterval
#        Jajob Execution interval.
#
# Mandatory: no
# Default: 1 (second)
# JaJobInterval=1

### Option: JaJobTimeout
#        Check the job icon timeout interval.
#
# Mandatory: no
# Range: 0-600
# Default: 30 (second)
# JaJobTimeout=30

### Option: JaRunInterval
#        Jarun Execution interval.
#
# Mandatory: no
# Default: 1 (second)
# JaRunInterval=1

### Option: JaMsgsndInterval
#        Jamsgsnd Execution interval.
#
# Mandatory: no
# Default: 1 (second)
# JaMsgsndInterval=1

### Option: JaStartTrappers
#        Number of pre-forked instances of jatrappers.
#
# Mandatory: no
# Range: 0-1000
# Default: 5
# JaStartTrappers=5
<p class="alert alert-info">Depending on the amount of agent/job, you will need to set this.
However, default value can handle small to medium size deployments.</p>

### Option: JaTrapperListenPort
#        Listen port for jatrapper.
#
# Mandatory: no
# Default: 10061
# JaTrapperListenPort=10061

### Option: JaAgentListenPort
#        Listen port for job agent.
#
# Mandatory: no
# Default: 10055
# JaAgentListenPort=10055
<p class="alert alert-info">Never change to other port, as you will need to configure all the agents to run on that port.
Currently, there is no flaxible agent port setting like zabbix.
</p>

### Option: JaExtjobPath
#        Directory to place an extended job.
#
# Mandatory: yes
# Default:
# JaExtjobPath=
JaExtjobPath=/etc/jobarranger/extendedjob

### Option: JaErrorCmdPath
#        Directory to place an application error notification.
#
# Mandatory: yes
# Default:
# JaErrorCmdPath=
JaErrorCmdPath=/etc/jobarranger/alert

### Option: JaLogMessageFile
#        Job Arranger application log message.
#
# Mandatory: yes
# Default:
# JaLogMessageFile=
JaLogMessageFile=/etc/jobarranger/locale/logmessage_64BIT.txt

### Option: JaFcopyTimeout
#        The communication timeout value at the time of a file transfer.
#
# Mandatory: no
# Range: 1-3600
# Default: 180 (second)
# JaFcopyTimeout=180

<p class="alert alert-info">In case, if you have plan to transfer large file which seems to not complete in `180` sec,
you will have to change this.
</p>

### Option: JaZabbixVersion
#        Specifies the version of Zabbix that job arranger uses.
#
# Mandatory: no
# Range: 1-2
# 1: zabbix 1.8
# 2: zabbix 2.0
# 3: zabbix 2.2
# Default: 1
# JaZabbixVersion=1
JaZabbixVersion=3

<p class="alert alert-info">Change according to Zabbix version
</p>

### Option: JaLaunchInterval
#        Immediate start up interval of jobnet.
#
# Mandatory: no
# Default: 1 (second)
# JaLaunchInterval=1

### Option: JaZabbixMessageFile
#        Zabbix status change message file directory.
#
# Mandatory: yes
# Default:
# JaZabbixMessageFile=
JaZabbixMessageFile=/etc/jobarranger/locale

### Option: JaExecutionUser
#        Specify the execution user of job Arranger Server.
#
# Mandatory: no
# Default: zabbix
# JaExecutionUser=zabbix
</pre>