---
  title: Training
  links:
  - url: /model/
    group: topics
  - url: /training/resources/tools/
    group: topics
  - url: /training/resources/specifications/
    group: topics
  - url: /training/domain-modeler/
    group: tracks
  - url: /training/iepd-developer/
    group: tracks
  - url: /training/iepd-implementer/
    group: tracks
  todo: Elaborate on intro and roles; add old training materials
---

## What is NIEM?

If you are just getting started, please head over to the main site at [niem.gov](https://www.niem.gov) to learn...

- [About NIEM](https://www.niem.gov/about-niem)
- [How to Get Started](https://www.niem.gov/getting-started)
- and much more!

## General topics

{% assign topicLinks = page.links | where: "group", "topics" %}
{% include icon-list.html links=topicLinks %}

## Training tracks

Choose from below for the kind of materials that will best fit your role in using NIEM:

{% assign trackLinks = page.links | where: "group", "tracks" %}
{% include icon-list.html links=trackLinks %}
