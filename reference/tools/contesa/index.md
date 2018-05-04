---
  title: ConTesA - Conformance Testing Assistant
  short: ConTesA
  links:
  - url: /reference/tools/contesa/tutorial/
  - url: /reference/tools/contesa/account/
---

*[NIEM]: National Information Exchange Model
*[NDR]: Naming and Design Rules
*[IEP]: Information Exchange Package
*[IEPD]: Information Exchange Package Documentation
*[ConTesA]: Conformance Testing Assistant
*[SSGT]: Subset Generation Tool
*[XML]: Extensible Markup Language
*[XSD]: XML Schema Definition
*[JSON]: JavaScript Object Notation
*[RDF]: Resource Description Framework

{{page.description}}

[ConTesA]({{site.data.links.contesa}}), or the **Con**formance
**Tes**ting **A**ssistant, is a web-based tool capable of
validating documents against the NIEM Naming and Design Rules
(NDR).

{:.features}
- Validates XML content against the automated NIEM NDR
- Leverages XML Schema, RelaxNG, Schematron, and more to test conformance
- Generates a conformance report available in XLS, HTML, and XML formats
- Handles single XML documents or zip archives of XML content
- Able to create user accounts with saved conformance reports

{:.note}
> Do not upload sensitive material to ConTesA.

{:.note}
> ConTesA cannot verify that a document is fully NIEM conformant;
> only that it passes the set of automated rules from the NDR.

| ConTesA User | Use Cases |
| --------- | --------- |
| [Domain Modeler](/training/domain-modeler) | Check if a given XML domain conforms to the automated NDR rules |
| [IEPD Developer](/training/iepd-developer) | Check if a local NIEM IEPD conforms to the automated NDR rules |
| [IEPD Implementer](/training/iepd-implementer) | Check if a local NIEM IEP conforms to the automated NDR rules and is consistent with the referenced IEPD |
