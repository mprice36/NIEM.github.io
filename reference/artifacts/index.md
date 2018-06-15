---
  title: Artifacts
  icon: fa-sitemap
  description: NIEM artifacts
  links:
  - url: /reference/artifacts/reference-schema-document/
    group: schema
  - url: /reference/artifacts/extension-schema-document/
    group: schema
  - url: /reference/artifacts/schema-subset-documents/
    group: schema
  - url: /reference/artifacts/reference-vs-extension/
    group: schema
  - url: /reference/artifacts/code-lists/
    group: special
  
---

{{ page.description }}

[Click here](overview) for a one-page overview of each of the major concepts; otherwise continue on to go through the concepts one-by-one - or jump directly to the one you need more information about.

## The Basics

The NIEM artifacts are the physical components created to package and represent the data model divided into several files.

{% assign basicLinks = page.links | where: "group", "schema" %}
{% include icon-list.html links=basicLinks %}

## Special

{% assign advancedLinks = page.links | where: "group", "special" %}
{% include icon-list.html links=advancedLinks %}
