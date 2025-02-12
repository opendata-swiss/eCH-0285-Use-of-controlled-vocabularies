# Access Rights; (florian/lien)

## Context
| **Predicate**                                                             | **Domain**         | **Range**            | **Description**                                                                                   |
|---------------------------------------------------------------------------|-------------------|----------------------|---------------------------------------------------------------------------------------------------|
| [dct:accessRights](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#dataservice-access-rights) | `dcat:DataService`    | `dct:RightsStatement` | Indicates who can access the resource or its security status.      |
| [dct:accessRights](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#dataset-access-rights) | `dcat:DataSet`    | `dct:RightsStatement` | Indicates who can access the resource or its security status.                       |

## Usage Note
- Use this property exclusively for statements about access restrictions (e.g., privacy, security, or policy-related restrictions).
- The [European Access Rights Controlled Vocabulary](http://publications.europa.eu/resource/authority/access-right) SHOULD be used. Adapt categories definitions as needed for specific use cases. 

## Example

```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.org/dataset/1> a dcat:Dataset ;
    dcat:distribution <http://example.org/distribution/1> .

<http://example.org/distribution/1> a dcat:Distribution ;
    dcat:downloadURL <http://example.org/download/data.csv> ;
    dct:accessRights <http://publications.europa.eu/resource/authority/access-right/PUBLIC> ;
    dct:title "Public Dataset CSV Distribution"@en  .
```


## Decisions (and Reasoning)
1. Retained the recommendation to use the EU Publications Office access rights vocabulary.
2. Refined the definition to ensure precise usage.
3. Added a detailed example to illustrate proper usage.

## Change log (vs. Version 2)
- Introduced a new example that adheres to the recommended controlled vocabulary. 

## Discussion
- Should only used for rough classification.
- Adapt the definition of the different categories for real use.
- Proper example needs to be added.

