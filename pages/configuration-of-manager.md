---
layout: default
title: Configuration of Job Manager
permalink: /configuration-of-manager/
redirect_from:
  - /configuration-of-manager.html
sitemap:
    priority: 0.7
    lastmod: 2016-06-24T00:00:00-00:00
---

# <i class="fa fa-keyboard-o"></i> Configuration of Job Manager

As described in System Architecture section, Job Arranger Manager (JAM) connects to the database using ODBC.

Thus you need configure:

*   ODBC
*   JAM config file


## ODBC

Configure ODBC Data source using User or System DSN.

Example here is using Postgres Unicode ODBC Driver.


![ODBC Setting]({{ site.url }}/img/jazicons/odbc.png)


## JAM config file

```
<JobconDBInfo>
  <DBInfo>
    <JobconName>JAZ-SVR-DEV</JobconName>
    <DBUser>username</DBUser>
    <DBPassword>password</DBPassword>
    <DBSource>JAZ-SVR-DEV</DBSource>
    <DBType>0</DBType>
    <HealthCheckFlag>0</HealthCheckFlag>
    <HealthCheckInterval>5</HealthCheckInterval>
    <JaZabbixVersion>3</JaZabbixVersion>
  </DBInfo>
  <DBInfo>
    <JobconName>JAZ-SVR-STG</JobconName>
    <DBUser>username</DBUser>
    <DBPassword>password</DBPassword>
    <DBSource>JAZ-SVR-STG</DBSource>
    <DBType>1</DBType>
    <HealthCheckFlag>0</HealthCheckFlag>
    <HealthCheckInterval>5</HealthCheckInterval>
    <JaZabbixVersion>3</JaZabbixVersion>
  </DBInfo>
</JobconDBInfo>
```

*   **DBType:** 0: MySQL, 1: PostgreSQL
*   **HealthCheckFlag:** Specify the health check if database is MySQL, in order to prevent the connection timeout with database.

    0 : Disable
    
    1 : Enable
    
    This will be ignored if DB is PostgreSQL.

*   **HealthCheckInterval:** Interval in minutes for health check. Only applicable if DB is MySQL.
*   **JaZabbixVersion:** Specify Zabbix Version. Default value is version 1.8 .

    1 - zabbix 1.8.x
    
    2 - zabbix 2.0.x
    
    3 - zabbix 2.2.x