
The **S**chema **S**ubset **G**eneration **T**ool ([SSGT]({{ site.data.links.ssgt }}))
enables you to search and explore the
content of the NIEM model. Additionally, you have the option of
building XML Schema subsets of a NIEM release for use in NIEM XML
exchanges. Based on the list of components selected by you
for the subset, the tool will calculate dependencies and generate
a valid set of schemas that are a subset of a release for
download as a zip file.

{:.features}
- Search and explore the content of NIEM
- Build XML Schema subsets of a release
  - Automatic management of component dependencies
  - Customize cardinality and nillable values
- Multi-release support
- API for selecting NIEM subset components (wantlist)

{:.note}
> A NIEM subset will contain only the user-selected elements and
> types from a release, plus any required dependencies. The
> subset will likely be much smaller than the corresponding full
> NIEM release.

| User | Use Cases |
| ---- | --------- |
| Domain modeler | n/a |
| IEPD developer | Search and explore NIEM components while mapping source requirements. <br> Search NIEM while modeling local extensions. <br> Create an XML schema subset of a release for use in an exchange. |
| IEPD implementer | n/a |
