---
  title: Properties
  icon: fa-lightbulb-o
  description: A property represents a concept, idea, or thing.
  links:
    - url: /reference/concepts/property/modeling/
    - url: /reference/concepts/property/element/
    - url: /reference/concepts/property/abstract/
    - url: /reference/concepts/property/substitutable/
    - url: /reference/concepts/property/attribute/
---

{% include_relative intro/index.md %}

## Kinds

In NIEM, there are two basic kinds of properties: elements and attributes.

**Attributes** can only ever be used to represent simple content (a value).  They do not exist independently; they must be carried by an element.

**Elements** can be used to represent simple content (a value) or complex content (an object).  In either case, an element can also carry attributes.

{:.example}
>This example lists 5 elements (each beginning with `nc:Person`) and 2 attributes (`structures:id` and `nc:personNameInitialIndicator`).
>```xml
><nc:Person>
>  <nc:PersonName structures:id="a123">
>    <nc:PersonGivenName>John</nc:PersonGivenName>
>    <nc:PersonMiddleName nc:personNameInitialIndicator="true">Q</nc:PersonMiddleName>
>    <nc:PersonSurName>Smith</nc:PersonSurName>
>  </nc:PersonName>
></nc:Person>
>```

Attributes cannot be extended, substituted, augmented, or have multiple occurrences.  Additionally, because NIEM uses attributes for referencing and linking data, metadata, and security markup, elements should be used over attributes whenever possible in order to support these features.  Over 99% of the properties in NIEM are elements.
