# Rights; (lien/lmi)

## Context
| **Predicate**                                                             | **Domain**         | **Range**            | **Description**                                                                                   |
|---------------------------------------------------------------------------|-------------------|----------------------|---------------------------------------------------------------------------------------------------|
| [dct:rights](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#catalog-rights) | `dcat:Catalog`    | `dct:RightsStatement` |  This property refers to a statement that specifies rights associated with the Catalogue.                            |
| [dct:rights](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#distribution-rights) | `dcat:Distribution`    | `dct:RightsStatement` | This property refers to a statement that specifies rights associated with the Distirbution                                 |

 * There is also Licence, which is specific for Licencing 
 * There is also Access Rights: Which is only stating if the dataset in the style of "open"/"closed"/"restricted". See (publications.europa.eu/resource/authority/access-right).
 * This is not in the meaning of a legal "applicable legislation". (False friend, right != Recht).
 * DCTERMS rights definition: "Typically, rights information includes a statement about various property rights associated with the resource, including intellectual property rights. Recommended practice is to refer to a rights statement with a URI. If this is not possible or feasible, a literal value (name, label, or short text) may be provided." https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/rights/ 
 * DCTERMS RightsStatment definition: "A statement about the intellectual property rights (IPR) held in or over a resource, a legal document giving official permission to do something with a resource, or a statement about access rights." https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/RightsStatement/ 

## Usage Note
- Prioritize using dct:license, dct:accessRights and for a link to a legal text dcat:applicableLegislation. Use dct:rights only for additional, specific rights information. 
- When using dct:rights, we advise you to use the [Open Data Rights Statement Vocabulary (ODRS)](http://schema.theodi.org/odrs/).
- To refer to a dct:RightStatement it is recommended to use an URI. 

## Decisions (and Reasoning)

1. Established an order of preference:
    - Evaluate dct:license, dct:accessRights, and dcat:applicableLegislation first.
    - Use dct:rights only if no other property is suitable.
2. Vocabulary to be used: the ODRS for rights statements.
3. Recommended to refer to rights statements with URI.

## Change log (vs. Version 2)
- Clarified when to use dct:rights to prevent inappropriate usage.
- Added an example.  

## Examples 
```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.org/dataset/1> a dcat:Dataset ;
    dcat:distribution <http://example.org/distribution/1> .

<http://example.org/distribution/1> a dcat:Distribution ;
    dct:format <http://publications.europa.eu/resource/authority/file-type/CSV> ;
    dcat:downloadURL <http://example.org/download/data.csv> ;
    dct:accessRights <http://publications.europa.eu/resource/authority/access-right/PUBLIC> ;
    dct:rights [  a odrl:Duty ;
        odrl:action <https://schema.org/RegisterAction>];
    dct:title "Public Dataset CSV Distribution"@en 
     .
```
