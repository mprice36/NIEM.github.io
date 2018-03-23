
The [Schema Subset Generator Tool (SSGT)](site.data.links.ssgt) enables users to search and explore the content of the NIEM model.  Additionally, users have the option of building XML Schema subsets of a NIEM release for use in NIEM XML exchanges.  Based on the list of components selected by the user for the subset, the tool will calculate dependencies and generate a valid set of schemas that are a subset of a release for download as a zip file.

{:.features}
- Search and explore the content of NIEM
- Build XML Schema subsets of a release
  - Automatic management of component dependencies
  - Customize cardinality and nillable values
- Multi-release support
- API for subset generation given a list of component selections (wantlist)

{:.note}
> The SSGT addresses the concern some people may have about NIEM being "too big".  The full 4.0 NIEM release has over 11,000 elements, almost 4,000 types, and dozens of namespaces.  A NIEM subset will contain only the user-selected elements and types from a release, plus any required dependencies.  This subset will likely be much smaller than the corresponding full release, improving processing and validation speeds, and simplifying the exchange for implementers.

| User | Use Cases |
| ---- | --------- |
| Domain modeler | Search and explore content from a domain or release |
| IEPD developer | Search and explore NIEM components while mapping source requirements <br> Search NIEM while modeling local extensions <br> Create an XML schema subset of a release for use in an exchange<br>  |
| IEPD implementer | Optional to search and explore NIEM content, but should not be necessary.  The IEPD itself should include all information and documentation necessary to implement the exchange. |
