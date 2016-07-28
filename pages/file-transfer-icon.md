---
layout: default
title:  File Transfer Icon
permalink:  /file-transfer-icon/
redirect_from: 
    - /file-transfer-icon.html
sitemap: 
    priority: 0.7
    lastmod: 2016-06-25T00:00:00-00:00
---

# File Transfer Icon

### Shape

![File Transfer Icon]({{ site.url }}/img/jazicons/file-transfer-icon.png)

### Description

By using this icon, you can transfer file from one host to another host.

Currently, file name with non-ascci is not allowed to transfer between different OS.

**Note** : File limit is 2GB.

### Setting

![File Transfer Setting]({{ site.url }}/img/jazicons/file-transfer-setting.png)

#### Details

You can provide id and name.

Source host

*   **Host name** : The host in which your file exists.
*   **Variable** : Alternative to **Host name**, hostname will be resolved from this variable.

Source file information

*   **Directory** : Directory in which your file exists.
*   **File name** : File name.

Destination host

*   **Host name** : The host on which your file will be transferred.
*   **Variable** : Alternative to **Host name**, hostname will be resolved from this variable.

Destination directory information

*   **Directory** : In this directory file will be transferred.
*   **Overwrite is permitted** : "on" this if you want overwritten.

*   **Force run** : Copy file even if the host is disabled in Zabbix.