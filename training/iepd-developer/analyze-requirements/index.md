---
title: Analyze Requirements
icon: fa-envelope-o
description: The analyze requirements phase is the next step you take in IEPD development.  
---

{{ page.description}}

{% include icon-list.html links=page.links %}

You have determined the IEPD requirements, and now you need to explicitly document them and their dependencies.

## Data Details

For example, the exchange goal could be the information in an immigrating person's passport. Make a list of the types of data available and what you want to include in the exchange.

| Main Item | Child Items | Notes |
| --- | --- | --- | --- |
| Name | GivenName<br>MiddleName<br>FamilyName | Do we want more than one middle name?<br>Is the order of Family Name and Given Name important? |
| Country of Origin |  | How many characters for country code? Determines the code list that may be used. |
| Issuing Authority |  |  |
| Birth Date | BirthCentury<br>BirthYear<br>BirthMonth<br>BirthDay | Order? Dd Mmmm Yyyy? |
| Sex |  | Assume F or M? |

