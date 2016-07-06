---
layout: default
title: Job Server Installation
permalink: /install-job-server-from-package/
redirect_from:
  - /install-job-server-from-package.html
sitemap:
    priority: 0.7
    lastmod: 2016-07-03T00:00:00-00:00
---

# <i class="fa fa-cloud-download"></i> Installing Job Server

## Requirements

### Operating Systems

*	**Red Hat Enterprise Linux 5.x later**
*	**CentOS 5.x later**

**Please check [Official Repository](https://ftf-support.fitechforce.com/redmine/projects/job-arranger-for-zabbix/repository) to verify which version you need and does it support your OS or not.**


### Hardware

There is no any specific requirement of hardware as far as your systems run on intel.

**Please check [Official Website](http://job-scheduler.fitechforce.com/) for more information.**

### Software

*	**Zabbix 1.8.x, 2.x, 3.x**
*	**MySQL 5.0 or later**
*	**Postgresql 9.1 or later**
*	**libss2 1.0.0 or later**

**You do not need to install any database because JAZ uses Zabbix database.**

**Please check [Official Website](http://job-scheduler.fitechforce.com/) for more information.**


## Installation

### Download
Download the required RPM files from [Official Repository](https://ftf-support.fitechforce.com/redmine/projects/job-arranger-for-zabbix/repository).

### Installing

Install by `rpm	` command.

`rpm -ivh jobarranger-server-yourdatabase-xxxxxxxx.rpm`
