---
  title: Reference Schema Documents
  short: Reference Schema Documents
  icon: fa-sitemap
  description: Description of reference schema documents.
---

{% include_relative intro/index.md %}

## Why Reference Schema Documents

A reference schema document is a required component of an IEPD. It represents a subset of the NIEM schema. The reference schema document contains the needs of the data exchange whose parts are semantically and conceptually identical to NIEM Core and the current NIEM domains. Data that are not well-matched in NIEM core and the other domains are handled in extension schema documents.

## Example

```xml
  <?xml version="1.0" encoding="US-ASCII"?>
  <xs:schema targetNamespace="http://release.niem.gov/niem/niem-core/3.0/" version="1" xsi:schemaLocation="http://release.niem.gov/niem/appinfo/3.0/ ../../appinfo/3.0/appinfo.xsd http://release.niem.gov/niem/conformanceTargets/3.0/ ../../conformanceTargets/3.0/conformanceTargets.xsd" ct:conformanceTargets="http://reference.niem.gov/niem/specification/naming-and-design-rules/3.0/#ReferenceSchemaDocument" xmlns:niem-xs="http://release.niem.gov/niem/proxy/xsd/3.0/" xmlns:structures="http://release.niem.gov/niem/structures/3.0/" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:appinfo="http://release.niem.gov/niem/appinfo/3.0/" xmlns:ct="http://release.niem.gov/niem/conformanceTargets/3.0/" xmlns:nc="http://release.niem.gov/niem/niem-core/3.0/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <xs:import schemaLocation="../../proxy/xsd/3.0/xs.xsd" namespace="http://release.niem.gov/niem/proxy/xsd/3.0/"/>
    <xs:import schemaLocation="../../structures/3.0/structures.xsd" namespace="http://release.niem.gov/niem/structures/3.0/"/>
    <xs:element name="DateRepresentation" abstract="true"/>
    <xs:element name="DateTime" type="niem-xs:dateTime" substitutionGroup="nc:DateRepresentation"/>
  </xs:schema>
```

## Advanced Structures and Components

Reference schema documents promote maximum reusability with other exchanges and need to be as simple in their structure and content as possible. The use of wildcards and anonymous components is strongly discouraged because they do not promote standardization and reusability due to their arbitrary nature.
