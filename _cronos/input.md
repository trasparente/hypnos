---
title: Input
order: 1
date: 2016-03-23 10:20:00
form:
  file: time.csv
  fields:
    date:
      type: date
      default: today
    category: true
    details: true
    value:
      type: number
    duration: true
---
{% include widgets/form.html %}
{:.language-liquid}
    {% raw %}{% include widgets/form.html %}{% endraw %}

<details markdown=1>
<summary><code>csv=time</code></summary>

{% include widgets/view.html csv="time" %}

</details>