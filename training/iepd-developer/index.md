---
  title: IEPD Developer
  icon: fa-envelope-o
  description: An Information Exchange Package Documentation (IEPD) Developer designs, builds, and validates the components (artifacts) of an Information Exchange Package (IEP). The process consists of a six-phase lifecycle.
---

{{ page.description}}

{% include icon-list.html links=page.links %}

## IEPD Lifecycle

1. **[Scenario Planning](scenario-planning/ "Scenario Planning")**: During the Scenario Planning phase, you review background information related to your information exchange, assess resource impact, understand business context, and identify information exchange business scenarios.
1. **[Analyze Requirements](analyze-requirements/ "Analyze Requirements")**: During the Analyze Requirements phase, the selected information exchange scenario is further elaborated to understand and document the business context and data requirements.
1. **[Map and Model](map-and-model/ "Map and Model")**: During the Map and Model phase, you begin the creation of IEPD components for your exchange content model based on your information exchange requirements.  You start with the mapping document, which matches your exchange data elements to the NIEM data model.
1. **[Build and Validate](build-and-validate/ "Build and Validate")**: During the Build and Validate phase, you create a set of exchange-specific, NIEM-conformant XML schemas that implement the exchange content model created for the exchange and validate them. Components in this phase also include other XML documents generated from NIEM tools (e.g., Wantlist).
1. **[Assemble and Document](assemble-and-document/ "Assemble and Document")**: During the Assemble and Document Phase, you prepare and package all related files for the IEPD into a single, self‐contained, self-documented, portable archive file. You then should perform a peer review to ensure artifact consistency within the IEPD and with other IEPDs.
1. **[Publish and Implement](publish-and-implement/ "Publish and Implement")**: During the last phase, the Publish and Implement phase, you implement the IEPD into production and publish the IEPD for search, discovery, and reuse.
