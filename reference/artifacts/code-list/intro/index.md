Reference schema documents are one of the principle NIEM artifacts. They provide the authoritative definitions of broadly reusable schema components (e.g., data elements, types) from a given namespace (e.g., Core (nc), Screening (scr)).

{:.features}
>
> - Explicit Conformance Target specified in the NDR
> - Broadest and most fundamental definitions of namespace components
> - Provides authoritative semantics for namespace components
> - Serves as the basis for IEPDs and Extension Schema Documents

{:.note}
> The rules for development of reference schema documents are more restrictive than all other NIEM components to enforce the documents’ features:
> - Has a uniform document structure.
> - Does not restrict other data definitions.
> - Does not use XML Schema's restriction mechanism **`xs:restriction`**.
> - Made as regular and simple as possible.

| User | Use Cases |
| --------- | --------- |
| [Domain Modeler](/training/domain-modeler) | Create a set of reuseable components defining conformance to the domain structure. |
| [IEPD Developer](/training/iepd-developer) | Normalize broadly reuseable schema components relavent to future IEPDs. |
| [IEPD Implementer](/training/iepd-implementer) | N/A |
