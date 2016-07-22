---
layout: default
title:  Conditional Branch Icon
permalink:  /conditional-branch-icon/
redirect_from: 
    - /conditional-branch-icon.html
sitemap: 
    priority: 0.7
    lastmod: 2016-07-22T00:00:00-00:00
---

# Conditional Branch Icon

### Shape

![Conditional Branch Icon]({{ site.url }}/img/jazicons/if-icon.png)

### Description

This icon is used to compare a value against a variable.

It is very useful when you want to separate the execution flow based on certain condition.

Such as by using [Information Acquisition Icon]({{ site.url }}/information-acquisition-icon/) ,check if today is a specific day then execute this job otherwise continue to execute regular job.

**Note** This icon results a boolean value. You can right-click the output flow-arrow of this icon to set **TREU** or **FALSE** settings.

### Setting

![Conditional Branch Setting]({{ site.url }}/img/jazicons/if-setting.png)

#### Details

You can provide id and name.

*   **Variable** : The value of this variable will be compared against **Comparison value**.
*   **Processing method** : Check for a numeric value or character string.
    You can provide multiple numeric value such as `x`, `x,y` , `x-y` with range support.
    **Regular expressions** are available for character string value.
*   **Comparison value** : The value to compare.