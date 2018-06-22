---
  title: Simple Types
  icon: fa-square
  description: A simple type is a structure that represents a simple value only.
  links:
    - url: /reference/concepts/type/simple/modeling/
    - url: /reference/concepts/type/simple/xml/
    - url: /reference/concepts/type/simple/json/
    - url: /reference/concepts/type/simple/list/
      group: kind
    - url: /reference/concepts/type/simple/union/
      group: kind
---

{% capture doggie %}
{% include_relative intro/index.md %}
{% endcapture %}
{{ doggie | markdownify}}

## Provided types

Common simple types provided by XML include `xs:string`, `xs:token`, `xs:date`, `xs:date-time`, `xs:integer`, `xs:decimal`, and `xs:boolean`.

Simple types provided by JSON are `string`, `integer`, `decimal`, and `boolean`.  Dates are simply strings in JSON, but if they follow the format set by ISO 8601, they can be converted into dates in JavaScript.

## Other kinds

In addition to a simple type with facets, NIEM supports two additional kinds of simple types:

{% assign links = page.links | where: "group", "kind" %}
{% include icon-list.html links=links %}
