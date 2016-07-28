---
layout: default
title:  File Waiting Icon
permalink:  /file-waiting-icon/
redirect_from: 
    - /file-waiting-icon.html
sitemap: 
    priority: 0.7
    lastmod: 2016-06-25T00:00:00-00:00
---

# File Waiting Icon

### Shape

![File Waiting Icon]({{ site.url }}/img/jazicons/file-wait-icon.png)

### Description

Wait until or check if given file is created or not.

You can also delete that file after finish checking.

### Setting

![File Waiting Setting]({{ site.url }}/img/jazicons/file-wait-setting.png)

#### Details

You can provide id and name.

Host

*   **Host name** : The host on which you want to check.
*   **Variable** : Alternative to **Host name**, hostname will be resolved from this variable.


*   **File name** : Full File name.

Processing mode

*   **Waiting file creation** : Wait until the file is created or just continue if already created.
*   **Waiting file existence** : Only check if the file exists or not.


*   **Delete file** : After checking, delete file.
*   **Timeout(sec)** : In case of waiting for file creation, this icon will stop with error state after timeout seconds.

*   **Force run** : Perform processing even if the host is disabled in Zabbix.
