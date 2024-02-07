---
title: Time
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
{:toc}
- toc
{% include widgets/form.html %}
{:.language-liquid}
    {% raw %}{% include widgets/form.html %}{% endraw %}

{% include widgets/view.html csv="time" category="trash" sort='asc' %}
{:.language-liquid}
    {% raw %}{% include widgets/view.html csv="time" category="trash" sort='asc' %}{% endraw %}

{% include widgets/view.html csv="time" category="briefing" limit="4" sort="asc" %}
{:.language-liquid}
    {% raw %}{% include widgets/view.html csv="time" category="briefing" limit="4" sort="asc" %}{% endraw %}

{% include widgets/view.html csv="time" category="bill" limit="4" sort="asc" %}
{:.language-liquid}
    {% raw %}{% include widgets/view.html csv="time" category="bill" limit="4" sort="asc" %}{% endraw %}

{% include widgets/view.html csv="time" category="yaris, kangoo, citroen" title="cars" sort="asc" %}
{:.language-liquid}
    {% raw %}{% include widgets/view.html csv="time" category="yaris, kangoo, citroen" title="cars" sort="asc" %}{% endraw %}

<details markdown=1>
<summary><code>csv=time</code></summary>

{% include widgets/view.html csv="time" %}

</details>