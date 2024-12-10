# Creator / Publisher etc.

## Context
| **Predicate**                                                                 | **Domain**         | **Range**           | **Description**                                              |
|------------------------------------------------------------------------------|-------------------|---------------------|-------------------------------------------------------------|
| [dcat:creator](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_creator) | `dcat:Resource`    | `foaf:Agent`        | The entity (person, organization, or service) responsible for creating the resource (like a dataset). |
| [dcat:publisher](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_publisher) | `dcat:Resource`    | `foaf:Agent`        | The organization or entity that publishes the dataset, making it available for access or download. |
| [prov:qualifiedAttribution](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_qualifiedAttribution) | `dcat:Resource`    | `prov:Attribution`  | A detailed attribution statement about an agent's role in the creation, curation, or management of the dataset, supporting roles like custodian, owner, steward, etc. |


## Usage Note

## Decisions (and Reasoning)

## Discussion

  (Michael / Michèle)
  
  * Context:  Creator / Publisher Organisation | Qualified Attribution (DataCustodian / DataSteward / DataOwner/ ...)

  * Problematik: Currently no standardised publisher name

  * UID Organisations
  * Zefix Organisations
  
  * DCAT-AP CV to be used: 
    https://semiceu.github.io/DCAT-AP/releases/3.0.0/#controlled-vocabularies-to-be-used 
    publisher: https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/corporate-body

  * DCAT-AP CH:
    * UID - FOAF concept: ld.admin.ch/org/CHE-370.148.023
      * provide URIs and Labels as LD?
    * Department / Office https://ld.admin.ch/department/V / https://ld.admin.ch/office/V.1.6
    * Kanton -> Ämter (Empfehlung) -> CV nicht existent (Aufbauen?) -> I14Y Ämter / UID
    * Fallback / Wikidata: https://www.wikidata.org/wiki/Q1326584
      
* Not to be used:
    * Opendata.swiss Organization / https://www.dcat-ap.ch/vocabulary/publishers/20210623.html
