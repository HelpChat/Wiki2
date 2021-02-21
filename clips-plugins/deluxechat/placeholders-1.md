---
description: >-
  DeluxeChat provides PlaceholderAPI placeholders that you can utilize in any
  plugin that supports PlaceholderAPI. It also provides a few internal
  placeholders.
---

# Placeholders

{% hint style="info" %}
For the PlaceholderAPI placeholders to work you'll have to download the expansion by using the commands:   
/papi ecloud download DeluxeChat  
/papi reload
{% endhint %}

{% hint style="info" %}
The PlaceholderAPI placeholders start with %deluxechat\_.  
The others are just internal placeholders.
{% endhint %}

| Placeholder | Return Value | Description |
| :--- | :--- | :--- |
| %deluxechat\_is\_pm\_toggled% | Boolean | Shows if the person has private messages enabled or not. |
| %deluxechat\_pm\_recipient% | Text | Name of the person that the replay message will be sent to. |
| %deluxechat\_social\_spy\_enabled% | Boolean | Shows if the person has social spy enabled or not. |
| %player% | Text | One of the only 2 placeholders that you can use in socialspy. |
| %recipient% | Text | One of the only 2 placeholders that you can use in socialspy. |
| %server% | Text | Display the server names that you've set at server\_prefix option. |

{% hint style="info" %}
You can use any PlaceholderAPI placeholders in private messages format by using %recipient\_placeholder-here%.  
For example: %recipient\_player\_name% will display the recipient's name.
{% endhint %}

