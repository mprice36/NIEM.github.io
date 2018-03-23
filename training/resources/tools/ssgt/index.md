---
  title: Schema Subset Generation Tool (SSGT)
  short: SSGT
  description: The SSGT enables users to search and view the content of the NIEM model, and build XML Schema subsets for use in exchanges.
  links:
  - url: /training/resources/tools/ssgt/search/
  - url: /training/resources/tools/ssgt/explore/
  - url: /training/resources/tools/ssgt/subset/
  - url: /training/resources/tools/ssgt/options/
  todo: Move subset example snippet to subset page in the future
---

- TOC
{:toc}

## Overview

{% include_relative intro/index.md %}

## Subset Snippet

The following is a snippet showing the full declaration of type `PersonNameType` from the Core namespace in the 4.0 release:

```xml
  <xs:complexType name="PersonNameType">
    <xs:annotation>
      <xs:documentation>A data type for a combination of names and/or titles by which a person is known.</xs:documentation>
    </xs:annotation>
    <xs:complexContent>
      <xs:extension base="structures:ObjectType">
        <xs:sequence>
          <xs:element ref="nc:PersonNamePrefixText" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonGivenName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonMiddleName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonSurName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonNameSuffixText" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonMaidenName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonFullName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonNameCategoryAbstract" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonNameSalutationText" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonOfficialGivenName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonPreferredName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonSurNamePrefixText" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonNameAugmentationPoint" minOccurs="0" maxOccurs="unbounded"/>
        </xs:sequence>
        <xs:attribute ref="nc:personNameCommentText" use="optional"/>
      </xs:extension>
    </xs:complexContent>
  </xs:complexType>
```

The following shows a corresponding snippet from a **subset** of Core.

{:.note}
- In this case, only three elements from `nc:PersonNameType` were added to the subset.  Since the other elements in this type are not being used, they do not appear in this subset version of the Core schema.
- The cardinality in this subset has also been tightened from the typically optional and over-inclusive cardinality defined in the release.  In this case, the given name and surname must and may only occur once, while the middle name is optional and may be repeated.

```xml
  <xs:complexType name="PersonNameType">
    <xs:annotation>
      <xs:documentation>A data type for a combination of names and/or titles by which a person is known.</xs:documentation>
    </xs:annotation>
    <xs:complexContent>
      <xs:extension base="structures:ObjectType">
        <xs:sequence>
          <xs:element ref="nc:PersonGivenName" minOccurs="1" maxOccurs="1"/>
          <xs:element ref="nc:PersonMiddleName" minOccurs="0" maxOccurs="unbounded"/>
          <xs:element ref="nc:PersonSurName" minOccurs="1" maxOccurs="1"/>
        </xs:sequence>
      </xs:extension>
    </xs:complexContent>
  </xs:complexType>
```
