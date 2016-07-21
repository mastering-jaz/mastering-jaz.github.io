---
layout: default
title:  End Icon
permalink:  /end-icon/
redirect_from: 
    - /end-icon.html
sitemap: 
    priority: 0.7
    lastmod: 2016-06-25T00:00:00-00:00
---

# End Icon


### Shape

![End Icon]({{ site.url }}/img/jazicons/end-icon.png)

### Description

Every jobnet will end with an **end icon**.

You can have multiple end icons in a jobnet.

However if execution flow reach to an end icon, then jobnet will finish and no other end icon will be executed.

### Setting

![End Setting]({{ site.url }}/img/jazicons/end-setting.png)

#### Details

You can provide id and name if you want.

*   **Jobnet stop** : If you "on" the check box, job execution flow will be held/paused at this point. 
    Normally you won't need this to "on". However, in a large and nested jobnet, this might help with some situation such 
    as for "Don't execute the following subsequent jobs until some another dependent job is finished".

*   **End code(JOB_EXIT_CD)** : Normally each icon will have a `0` exit status by default. However if you want to change the exit status you can do.
    Such as for "If the previous job exit status was `xxx` then exit code of this jobnet must be `1`". Again this exit status can be checked by using 
    [Conditional Branch Icon a.k.a If Icon]({{ site.url }}/conditional-branch-icon/) or [Info Icon]({{ site.url }}/information-acquisition-icon/).