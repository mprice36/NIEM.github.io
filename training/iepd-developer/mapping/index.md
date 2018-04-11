#---
  title: IEPD Developer
  icon: fa-envelope-o
  description: An IEPD developer designs and manages the specification of an information exchange.
  links:
  - url: /model/
    newtab: true
  - url: /iepd-starter-kit/
    newtab: true
  - url: https://www.niem.gov/techhub/iepd-resources
    title: TechHub IEPD Resources
    description: Resources for IEPD developers on our TechHub site.
---

{{ page.description}}

{% include icon-list.html links=page.links %}

# Build and Validate an IEPD

An Information Exchange Package (IEP) contains Information Exchange Package Documentation (IEPD) that you need to generate and validate to ensure NIEM conformance:

- a mapping document that matches your exchange data elements to the NIEM data model

- XML schemas and other XML documents using NIEM tools

## Map and Model

### Mapping Document

The Mapping Document identifies how exchange data aligns to, or "maps," and reuses NIEM data objects. It is also referred to as a Component Mapping Template (CMT), Component Mapping Tool, or Mapping Spreadsheet.

- Demonstrates how data objects within an exchange map to data objects in NIEM by recording the degree of similarity

- Aids the identification process of objects that are not currently within NIEM and are candidates for inclusion in an extension schema

- Helps communicate the level of reuse in NIEM to business users/owners

A template is available for use on NIEM.gov.

![Mapping Document Example](mapping.png "Mapping Document Example")

#### Source Data Colummns (A)

| Source Container Type | Source Element | Source Data Type | Source Element Definition |
| --- | --- | --- | --- |
| The data source high-level object, class, or context of a set of data elements (e.g., person, vehicle, arrest) | The source element is a specific data element that is associated with the Source Container Type | Data type of the source element | The definition of the source element being mapped |
| **Example** |
| Person | DateofBirth | Date | Date of birth of a person |

#### NIEM Data Columns (B)

| NIEM Element | NIEM Element Path | NIEM Type | NIEM Element Definition |
| --- | --- | --- | --- |
| The name of the NIEM element the source element is mapped to | The path of the NIEM Element within the NIEM Model | The name of the type that is associated with the NIEM element | The standard definition for the NIEM element found in the element’s metadata |
| **Example** |
| nc:PersonBirthDate | nc:Person/nc:PersonBirthDate | nc:DateType | A date a person was born |

#### Mapping Column (C)

In a Mapping Document, you must search the NIEM model for appropriate data elements to map to local exchange data. If a NIEM element is found, the correlation of the source and NIEM elements is recorded here.

| Mapping |
| --- |
| Identifies how the source object or element maps to the NIEM object or element. |
| **Example** |
| Equivalent |

The Mapping "value" is the degree to which a source element maps to a NIEM element. Possible "values" include the following:

- Equivalent

- Partial

- No Match

You should include additional notes in the mapping document to provide reasoning and context.

### Mapping Process

The mapping process is composed of two steps:

1. Set up a Mapping Document

1. Search and Map NIEM Elements

#### Set up a Mapping Document

Do the following for the initial setup of the document:

1. Identify an object within the exchange content model as your starting point for entry in the document. This is the **Source Container Type** (a Source Container Type is the containing object to which elements belong).
1. Identify an element within that object. This is the **Source Element**.
1. Identify the data type for the element. This is the **Source Data Type**.
1. Provide a definition for the element. This is the **Source Element Definition**.
1. Repeat the previous steps for each object in the **Exchange Content Model**.

Example

Four columns should be filled in for every element within the exchange content model

![Mapping Setup Example](mappingsetup.png "Mapping Setup Example")

#### Search and Map NIEM Elements

Do the following to find NIEM elements that may have the same logical definition, semantics, and structure as source elements.

1. Use a NIEM tool (e.g., Schema Subset Generation Tool (SSGT)), find an element from a NIEM reference schema that “maps” to the exchange data element.

![Mapping Tool Example (SSGT)](mappingtool.png "Mapping Tool Example (SSGT)")

1. Try searching by name, for synonyms, conceptual meaning, or by type.

1. Map objects that are conceptually and semantically equivalent. If the alignment is not easily understood, it is better to extend.

1. Document the information about the NIEM data object, including the type of mapping (equivalent, partial, no match), if one is found.

#### Model Searching Tips

| Search Method | Explanation | Example |
| --- | --- | --- | --- |
| Name Variations | Searching for variations of a name can often yield results | Search for **Officer** instead of **Official** to yield **j:EnforcementOfficial** |
| Conceptual Meaning | Search for words that could be in the definition of the data object | Search for **Modified Charge** to yield **j:AmendedCharge** |
| Synonyms | Synonyms of the data object to find exactly what you are looking for | Search for **Facility** instead of **Building** to get different results |
| Containers | Use a more abstract term to find containers of the data objects | Search for **Person** instead of **Person Arrest** to get the maximum number of results |


## Build and Validate

### Create XML Schemas & Artifacts

### Validate XML Schemas

## Define an Exchange Content Model

    Exchange Content Models are graphical representations of elements for an information exchange, as well as their associated relationships. Exchange Content Models consist of objects, elements, associations, and possibly cardinality.  

## Five Basic IEPD XML Schemas

- Exchange

    Also known as document or root schemas, define the root element and overall structure of the message.
- Extension

    Define the data types and elements that are not contained within NIEM but are needed for an information exchange.
- Subset

    Contain a smaller subset of elements and types from the NIEM reference schemas that are used and needed as part of an exchange.
- Constraint

    Apply a set of available business rules or logic to the elements and how they are represented.
- Reference

    Serve as the authoritative definition schema for the NIEM namespace.

## Other NIEM XML Artifacts

XML artifacts aid in the understanding and representation of an information exchange.

- XML Instances

    Used as example messages that validate against the previously defined IEPD schemas.
- Wantlists

    XML documents that specify the elements and types that are needed from NIEM and will be used in an exchange.
- Code lists

    Reference lists that are used to constrain values for a given element to a predetermined list.
- Stylesheets

    Provide formatting or transformation for the data used within an exchange.

### IEPD Artifacts

Artifacts are the deliverables in the IEPD development process. Some artifacts are required while others are recommended.

The required and recommended artifacts associated with each phase of the IEPD lifecycle are highlighted here.

### Map and Model Artifacts

The artifacts associated with the Map and Model phase include the Exchange Content Model and mapping document.

- Exchange Content Model is a graphical representation of the data and relationships involved in the information exchange.

- The mapping document is created to align elements identified in your exchange content model to the NIEM data model.

None of the artifacts indicated in this phase are required, but are recommended.

### Build and Validate Artifacts

The artifacts associated with the Build and Validate phase include subset schema, extension schema, wantlist, constraint schema, and exchange schema, among other artifacts such as reference schema and XML stylesheets. Typical artifacts you will see include the following:

- Subset schema is a subset of the NIEM schemas, whose components are taken entirely from the parent reference schema while excluding those components that are unnecessary for a given exchange.

- Exchange schema is a NIEM-conformant schema that describes the data to be exchanged. XML stylesheets show how the data in the XML message can be formatted to be presentable.

- Wantlist is a tool-specific construct used in the Subset Schema Generation Tool (SSGT) to save and reuse schema subsets of the overall NIEM data model. Simply, it is those items that you want from NIEM.

- Constraint schema restricts or constrains content that appears in instances of the subset schema.

- Extension schema is a NIEM conformant schema that defines data elements that are to be used in an exchange but do not exist in the NIEM data model, which therefore must be added to the schema. The exchange schema is a required artifact for this phase.

Note that a NIEM-conformant IEPD is required to contain at least one schema that is either a NIEM Reference Schema or a Subset Schema

### Assemble and Document Artifacts

The artifacts associated with the Assemble and Document phase include master document, catalog, change log, and sample XML instances.

- Master document is used to organize the required documentation and provide business and functional context of the information exchange.

- Catalog is a file that details the structure of the IEPD and links to each of the artifacts within the IEPD.

- Change log is a file representing all of the changes made to the schema files of a domain update.

- Sample XML instances are sample XML data that can be used to test the XML schemas.

The master document, catalog, change log, and sample XML instances are all required artifacts.

### Publish and Implement Artifacts

For the Publish and Implement phase, while no artifacts are required, you should publish the IEPD for search, discovery, and reuse, as well as implement the exchange.

As a best practice, include many of the artifacts listed here, not just the required ones.

### Maintain an Exchange

To maintain an IEPD, keep in mind the following:

- Ensure that any changes to an information exchange are correctly reflected within the IEPD.

- Establish a governance process within the organization to actively manage changes made to IEPDs. A governance process controls and prioritizes changes to information exchanges. The lack of a governance process can lead to problems related to multiple versions of an IEPD and a lack of awareness of changes that were implemented.

- Since the IEPD may be reused, it is critical to update IEPDs as changes are made. The change log and documentation within an IEPD should be updated whenever changes are made.

- When changes are made to an IEPD, publish the new version to the repository.

- Choosing to not maintain an IEPD inhibits reuse within and outside the organization.

## IEPD Content

### Mapping Documents in IEPD Development

#### Mapping Document

Mapping Documents are an important part of IEPD development. The Mapping Document is a document that identifies how exchange data aligns to, or "maps," and reuses NIEM data objects.

- It demonstrates how data within an exchange map to data objects in NIEM by documenting the degree of similarity.

- It aids in the identification process of objects that are not currently within NIEM and are candidates for inclusion in an Extension Schema, and potentially in NIEM in the future.

- It helps communicate the level of reuse in NIEM to business users/owners.

A mapping document can also be referred to as a Component Mapping Template, a Component Mapping Tool, or a Component Mapping Spreadsheet.

The mapping document is an effective tool for documenting how the NIEM data model was reused. A template is available for use on NIEM.gov.

The mapping document is a tool used to bridge the gap between exchange data and how that exchange data is represented in NIEM. The mapping document also identifies all objects from the exchange content model to determine where NIEM reuse can occur or where NIEM requires extension.

#### Mapping Document Example

Mapping Documents are commonly referred to as Component Mapping Templates (CMTs) and use spreadsheets with a common set of columns. The following is an example of a CMT that documents the exchange to NIEM alignment.

![Mapping Document Example](mapping.png "Mapping Document Example")

- The Source Data Columns describe the locally defined data that will be mapped to NIEM. This information was probably recorded when the Exchange Content Model was being built. Depending on the exchange, it is likely that each exchange partner will have different information for these columns with the end goal of all showing NIEM alignment.

- The Mapping Column documents the alignment of the “Source Data” and “NIEM Data.” This “mapping value” will aid in the decision to place which XML elements and types in which XML Schemas.

- The NIEM Data Columns document the NIEM data objects to be reused in the IEPD’s XML schema. This means that for these cases, the NIEM element and type names will be used.

Note:
These or similar columns are the most commonly used for mapping documents. One of the goals of creating IEPDs is to promote reusability, and the more documentation available, the easier reuse becomes; therefore, more information is always helpful.

#### Exchange Content Model

As a data modeling tool, the Exchange Content Model should identify all of the data necessary for an exchange.  Objects in the exchange content model are represented in the Mapping Document. Associations and cardinality are not typically represented, but certainly can be, in the Mapping Document. You do not have to explicitly use data objects from the NIEM data dictionary, especially when depicting extension elements.

#### XML Schemas

After completing a Mapping Document, elements and types can be identified for inclusion in NIEM subset schemas or extension. Additionally, if a "container" data object (complex XML element) in NIEM is reused, the object will not be able to hold character data.

- Its Purpose

- The purpose and components of source data, NIEM data, and mapping columns

### The Mapping Process
