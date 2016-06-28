---
layout: default
title: Software components Overview
permalink: /jaz-components-overview/
redirect_from:
  - /jaz-components-overview.html
sitemap:
    priority: 0.7
    lastmod: 2016-06-24T00:00:00-00:00
---

# <i class="fa fa-object-group"></i> Software components of Job Arranger for Zabbix


### Job Arranger for Zabbix consists of several major software components, the responsibilities of which are outlined below.


### **Server**

**[Job Server]({{ site.url }}/job-server-concept/)** is the central component of the software. It is responsible for starting up jobnets based on the schedule and calendar. It command Job Agents to execute defined jobs.
It also receive agent sent data,  process some external call requests. Moreover, it performs agentless jobs execution.

### **Agent**

**[Job Agents]({{ site.url }}/job-agent-concept/)** are deployed on each target host in order to execute jobs. 
Agents receive jobs from server which need to run. After executing jobs, agent sent the results data back to server.

### **Manager**

**[Job Manager]({{ site.url }}/job-manager-concept/)** is a window application which users can use to create jobs, schedule and calendar. User can run the jobs, hold a job, skip a job, force stop a job etc.
Users can also monitor the executing jobs.

These components communicate with each other to execute and monitor the jobs.

[Check how these components communicate with each other]({{ site.url }}/system-architecture/)