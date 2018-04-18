
[The Conformance Testing Assistant (ConTesA)]({{ site.data.links.contesa }}) tests NIEM XML schemas for conformance to the NIEM Naming and Design Rules (NDR).

A number of NDR rules cannot be tested programmatically.  ConTesA cannot verify that a schema is fully NIEM conformant; only that it passes the provided set of automated rules.

{:.features}
- Users may upload a single schema or a zip file
- Checks schemas against Schematron rules from the NDR>
- Generates a conformance report available as a spreadsheet, HTML file, and XML file.

{:.note}
> Do not upload sensitive materials.

| User | Use Cases |
| ---- | --------- |
| Domain modeler | Check that a XML domain schema submission conforms to the automated NDR rules |
| IEPD developer | Check that a local NIEM XML schema conforms to the automated NDR rules <br> Generate a conformance report for an IEPD |
| IEPD implementer | n/a |
