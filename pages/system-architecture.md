---
layout: default
title: System Architecture of Job Arranger for Zabbix
permalink: /system-architecture/
redirect_from:
  - /system-architecture.html
sitemap:
    priority: 0.7
    lastmod: 2016-06-22T00:00:00-00:00
---

# <i class="fa fa-cogs"></i> System Architecture of Job Arranger for Zabbix


### [JAZ components]({{ site.url }}/jaz-components-overview/) contains following three components.

*   **Job Server** - centrally manages the entire jobs
*   **Job Agents** - installed on each server to execute jobs commanded from Job Server
*   **Job Manager** - GUI client to design, schedule, execute and monitor the jobs centrally

These components communicate with each other to execute and monitor the jobs.



**The following diagram shows the architecture of Job Arranger for Zabbix, without Zabbix components.**

![Diagram1]({{ site.url }}/img/jaz-arch1.png)



**The following diagram shows the architecture of Job Arranger for Zabbix, with Zabbix components.**

![Diagram2]({{ site.url }}/img/jaz-arch2.png)



**The following diagram shows a more complete real-world deployment architecture.**

![Diagram3]({{ site.url }}/img/jaz-arch3.png)