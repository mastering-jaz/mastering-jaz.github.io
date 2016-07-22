---
layout: default
title:  Job Icon
permalink:  /job-icon/
redirect_from: 
    - /job-icon.html
sitemap: 
    priority: 0.7
    lastmod: 2016-07-22T00:00:00-00:00
---

# Job Icon

### Shape

![Job Icon]({{ site.url }}/img/jazicons/job-icon.png)

### Description

Job icon is the icon which allow to execute command or script on a specified target host.

### Setting

![Job Setting]({{ site.url }}/img/jazicons/job-setting.png)

#### Details

You can provide id and name.

*   **Host name** : Specify a target host on which command or script will be executed.
*   **Variable** : Alternative to **Host name**, host name will be resolved from an environmental variable which is within this icon context.
*   **Stop Command** : In case, if you force stop the running job, `SIGKILL` is sent to job executing process. 
    If you want to provide custom command to execute for the force stop action, the you can provide with this.
*   **Exec** : You can directly provide the command or script with or without parameter.
*   **Job Variable** : You can provide custom variable to the **Exec** execution context.
*   **Jobcontrol variable** : Built-in variable for this execution context, you need to "on" the check box to use it.
*   **Timeout warning** : After `x` minutes a timeout message will occurs. Providing a timeout value does not stop executing job.
*   **Job stop code** : You can provide **numbers** to stop job execution. If the return code of command is `x` or `x,y` or between `x-y`, then stop this job, which will results in error state.
*   **Force run** : The default behavior of JAZ is that if the target host is disabled in Zabbix then job will not run on that host and job execution results in error. 
    However, if you want to run the job even if target host is disabled then you should "on" this check box.
*   **Continue** : The default behavior of JAZ is that if a job execution results in error then execution flow will be stopped at that point. 
    If you are sure enough that you understand what you are doing and want to continue the execution flow even if job executed resulted in error, then perhaps you may like to "on" this check box.
*   **Run user** : Job will be run with this user. Your OS must have the user created.
*   **Password** : Windows need password along with **Run user**, this will be ignored for other OS.