---
title: practices
form:
  file: practices.csv
  fields:
    date:
      type: date
      default: today
    serie:
      type: select
      options: [0,1,2,3,4]
      default: 1
---
<figure>{% include ashtanga_logo.html %}</figure>

{% include widgets/calendar.html csv='practices' property='serie' %}

<div class='flex'>
<div markdown='1'>

|{{ site.time | date: "%s" | minus: 5097600 | date: "%-d/%-m" }}|Practices||%
|--|--|--|--
|<span style='visibility:hidden'>00</span>60|{{ total }}|<progress max="60" value="{{ total }}"></progress>|{{ total | times: 100 | divided_by: 60 }}
{% assign year = site.time | date: "%Y" %}
{% assign day = site.time | date: "%j" %}
{% assign years = site.data.practices | sort: "date" | reverse | group_by_exp: "item", "item.date | slice: 0, 4" %}
|Year|Practices||%
|-|-|-|
{% for y in years %}|{{ y.name }}|{{ y.items.size }}|{% if y.name == year %}{% assign prog = y.items.size | times: 100 | divided_by: day %}{% else %}{% assign prog = y.items.size | times: 100 | divided_by: 365 %}{% endif %}<progress max="100" value="{{ prog }}"></progress>|{{ prog }}
{% endfor %}
</div>
<div markdown='1'>
|Serie|Practices|First|Last
|--:|--:|--:|--:|
|<span class='color-muted'>Null</span>|{{ site.data.practices | where: "serie", 0 | size }}|{% include widgets/first.html data=site.data.practices field='serie' value='0' %}|{% include widgets/last.html data=site.data.practices field='serie' value='0' %}
|<span class='color-green'>First</span>|{{ site.data.practices | where: "serie", 1 | size }}|{% include widgets/first.html data=site.data.practices field='serie' value='1' %}|{% include widgets/last.html data=site.data.practices field='serie' value='1' %}
|<span class='color-red'>Second</span>|{{ site.data.practices | where: "serie", 2 | size }}|{% include widgets/first.html data=site.data.practices field='serie' value='2' %}|{% include widgets/last.html data=site.data.practices field='serie' value='2' %}
|Total|{{ site.data.practices.size }}

{% include widgets/form.html %}
</div>
</div>