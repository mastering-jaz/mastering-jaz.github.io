---
layout: default
title:  Reboot Icon
permalink:  /reboot-icon/
redirect_from: 
    - /reboot-icon.html
sitemap: 
    priority: 0.7
    lastmod: 2016-06-25T00:00:00-00:00
---

# Reboot Icon

### Shape

![End Icon]({{ site.url }}/img/jazicons/reboot-icon.png)

### Description

Whenever you want to reboot a server, this is the icon you should be interested in.

### Setting

![End Setting]({{ site.url }}/img/jazicons/reboot-setting.png)

#### Details

You can provide id and name.

*   **Host name** : Select the host you want to reboot.
*   **Variable** : Alternative to **Host name**, hostname will be resolved from this variable.

Processing mode

*   **Force reboot** : Force reboot the server(i.e kill all running jobs on host and then reboot).
*   **Reboot after Completing Jobs** : Wait until all running jobs are finished. This can be ignored by setting up **Timeout**.

*   **Timeout** : Only applicable for **Reboot after Completing Jobs**, force reboot the server after `x` seconds.
    Valid values is from `0` to `9999`. If `0` is specified, it represents unlimited seconds.
*   **Timeout warning(minute)** : Produced a timeout message in respective log and reboot icon color will be changed to orange. 

*   **Force run** : If this is "on" then it don't care if the host is disabled in Zabbix. Just do reboot.