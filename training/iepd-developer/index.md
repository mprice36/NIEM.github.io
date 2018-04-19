---
  title: IEPD Developer
  icon: fa-envelope-o
description: An Information Exchange Package Documentation (IEPD) Developer designs, builds, and validates the components (artifacts) of an Information Exchange Package (IEP). This includes a Mapping Document that matches your exchange data elements to the NIEM data model, and XML schemas and other XML documents generated from NIEM tools.
  links:
  - url: /reference/concepts/
    newtab: true
  - url: /reference/content/
    newtab: true
  - url: /reference/releases/
    newtab: true
  - url: /reference/tools/ssgt/
    newtab: true
  - url: /reference/tools/movement/
    newtab: true
  - url: /reference/tools/contesa/
    newtab: true
  - url: /reference/tools/migration/
    newtab: true
  - url: /reference/specifications/code-lists/
    newtab: true
  - url: /iepd-starter-kit/
    newtab: true
  - url: https://www.niem.gov/techhub/iepd-resources
    title: TechHub IEPD Resources
    description: Resources for IEPD developers on our TechHub site.
---

{{ page.description}}

{% include icon-list.html links=page.links %}

# IEPD Lifecycle

This training section covers the six phases of the IEPD Lifecycle:

1. **Scenario Planning**: During the Scenario Planning phase, you review background information related to your information exchange, assess resource impact, understand business context, and identify information exchange business scenarios.
1. **Analyze Requirements**: During the Analyze Requirements phase, the selected information exchange scenario is further elaborated to understand and document the business context and data requirements.
1. **Map and Model**: During the Map and Model phase, you create an exchange content model based on your information exchange requirements. The Exchange Content Model is then mapped to the NIEM data model.
1. **Build and Validate**: During the Build and Validate phase, you create a set of exchange-specific, NIEM-conformant XML schemas that implement the exchange content model created for the exchange.
1. **Assemble and Document**: During the Assemble and Document Phase, you prepare and package all related files for the IEPD into a single, self‐contained, self-documented, portable archive file.
1. **Publish and Implement**: During the last phase, the Publish and Implement phase, you implement the IEPD into production and publish the IEPD for search, discovery, and reuse.

## Map and Model

The IEPD consists of the following:

- Mapping Document that matches your exchange data elements to the NIEM data model:<br>[Mapping Process and Document](mapping/ "Mapping Process and Document")
- XML schemas and other XML documents generated from NIEM tools:<br>[Generate XML Schemas and Other XML Documents and Validate Them](schemas/ "Generate XML Schemas and Other XML Documents and Validate Them")
