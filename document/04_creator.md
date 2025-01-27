# Creator / Publisher etc. (misp/lmi)

## Usage Note (will only be in the Standard)
* Form
  * In general as bulletpoints. (rougly up to 2-3).
  * Check first with the already available usage note.
* Content:
  * Recomendation regarding a controlled vocabulary to use.
    * Do we have a cascade of recomendations?
    * Decision tree if applicable. (If geodata, if on federal level, if ...)
  * The links (as references) to the controlled vocabularies.
  * A general example for the property. (More detailed examples go to the eCH-0285).
  * Link to the eCH-0285 aid.

## Context

### Domain / Range / Short description
| **Predicate**                                                                 | **Domain**         | **Range**           | **Description**                                              |
|------------------------------------------------------------------------------|-------------------|---------------------|-------------------------------------------------------------|
| [dcat:creator](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_creator) | `dcat:Resource`    | `foaf:Agent`        | The entity (person, organization, or service) responsible for creating the resource (like a dataset). |
| [dcat:publisher](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_publisher) | `dcat:Resource`    | `foaf:Agent`        | The organization or entity that publishes the dataset, making it available for access or download. |
| [prov:qualifiedAttribution](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_qualifiedAttribution) | `dcat:Resource`    | `prov:Attribution`  | A detailed attribution statement about an agent's role in the creation, curation, or management of the dataset, supporting roles like custodian, owner, steward, etc. |

| **Predicate**                                                                 | **Domain**         | **Range**           | **Description**                                              | **Usage note**                                             |
|------------------------------------------------------------------------------|-------------------|---------------------|-------------------------------------------------------------|------------------------------------------------------------|
| [dcat:creator](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_creator) | `dcat:Resource`   | `foaf:Agent`        | An entity responsible for producing the dataset. | Resources of type foaf:Agent are recommended as values for this property. See also 	DCAT 3 - 6.12 Class: Organization/Person | 
| [dcat:publisher](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_publisher) | `dcat:Resource`   | `foaf:Agent`        | This property refers to an entity (organisation) responsible for making the Dataset available. | The organisation MUST be the one that has published the dataset (in the legal sense, not the technical sense), i.e. that has decided to grant rights of use to third parties. CV to be used: LINDAS Vocabulary for departments  <a href="https://ld.admin.ch/department/V">https://ld.admin.ch/department/V</a> (I-V) and for offices <a href="https://ld.admin.ch/office/V.1.6</a>./li> Fallback: We recommend using the correspondend entry in Wikidata as CV: for example Entry of the <a href="https://www.wikidata.org/wiki/Q1326584">Federal Electricity Commission</a>. |
| [prov:qualifiedAttribution](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_qualifiedAttribution) | `dcat:Resource`   | `prov:Attribution`  | This property refers to a link to an Agent having some form of responsibility for the dataset | Used to link to an Agent where the nature of the relationship is known but does not match one of the standard [ DCTERMS ] properties ( dcterms:creator , dcterms:publisher ). Use dcat:hadRole on the prov:Attribution to capture the responsibility of the Agent with respect to the Resource. See DCAT 3 - 15.1 Relationships between datasets and agents for usage examples.




### Examples
* Concrete examples with the use of the full URIs.
* Examples in Turtle.
* Per case at least one example.

## Decisions (and Reasoning)
* If there are other possibilities to solve the same problem. State which one, and why we decided against it.

## Change log (vs. Version 2)
* What change, and which advantage it brings.



## Discussion (will be removed after integrated to the above chapters)

  Michael / Michèle
  
  * Context:  Creator / Publisher Organisation | Qualified Attribution (DataCustodian / DataSteward / DataOwner/ ...)

  * Problematik: Currently no standardised publisher name

  * UID Organisations
  * Zefix Organisations
  
  * DCAT-AP CV to be used: 
    https://semiceu.github.io/DCAT-AP/releases/3.0.0/#controlled-vocabularies-to-be-used 
    publisher: https://op.europa.eu/en/web/eu-vocabularies/concept-scheme/-/resource?uri=http://publications.europa.eu/resource/authority/corporate-body

  * DCAT-AP CH:
    * UID - FOAF concept: ld.admin.ch/org/CHE-370.148.023
      * Universitäten / Forschungsinstitute ?
      * Gemeinden ?
      * Vereine, nicht eingetragen OpenGLAM?
      * provide URIs and Labels as LD?
    * Department / Office https://ld.admin.ch/department/V / https://ld.admin.ch/office/V.1.6
    * Kanton -> Ämter (Empfehlung) -> CV nicht existent (Aufbauen?) -> I14Y Ämter / UID
      * https://www.dcat-ap.de/def/contributors/ 
    * Fallback / Wikidata: https://www.wikidata.org/wiki/Q1326584
      
* Not to be used:
    * Opendata.swiss Organization / https://www.dcat-ap.ch/vocabulary/publishers/20210623.html

* To be clarified: How is it handled with https://www.dcat-ap.de/def/contributors/

* Einfacher durch eigenes Voka mit Links zu anderen Listen ?
