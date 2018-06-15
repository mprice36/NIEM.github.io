Schema subset documents are a collection of NIEM conformant schema documents that compose an
XML Schema. When schemas are packaged together as IEPDs or Domains, they form a collection
called a Schema Subset.

{:.features}
>
> - Explicit Conformance Target specified in the NDR
> - Represent a closed unit of the a NIEM conformant schema document assembly
> - Composed from Reference, Extension, Constraint, etc. schema documents
> - Serves as the basic unit for composing an IEPD

{:.note}
> Schema subset documents are not a particular document; rather, they are a collection of
> schema documents. However, they have a designated conformance target to note that make a
> stronger point.

| User | Use Cases |
| --------- | --------- |
| [Domain Modeler](/training/domain-modeler) | Create a set of reuseable components defining conformance to the domain structure. |
| [IEPD Developer](/training/iepd-developer) | Normalize broadly reuseable schema components relavent to future IEPDs. |
| [IEPD Implementer](/training/iepd-implementer) | N/A |
