
A simple type is a structure that represents a simple value only.

Simple types are data structures like strings, numbers, and booleans.  They can also be customized with [facets](/reference/concepts/facet) so that only a certain range of numbers, or a certain set of codes, for example, are allowed.

Simple types can be used in two ways in the model:

- As the type of [attributes](/reference/concepts/property/attribute), which by definition cannot have a complex type.
- As the base of corresponding [complex types with simple content (CSCs)](/reference/concepts/type/csc), which can be assigned to elements.

{: .example}
>
>- Core defines attribute `personNameInitialIndicator`.  Its type is a boolean - a simple type.
>- Core defines simple type `AddressCategoryCodeSimpleType`, which constrains a string down to a few possible codes, like `residential` and `business`.
