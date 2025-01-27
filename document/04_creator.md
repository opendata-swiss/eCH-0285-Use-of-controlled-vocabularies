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

| **Predicate**                                                                 | **Domain**         | **Range**           | **Description**                                              | **Usage note**                                             |
|------------------------------------------------------------------------------|-------------------|---------------------|-------------------------------------------------------------|------------------------------------------------------------|
| [dcat:creator](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_creator) | `dcat:Resource`   | `foaf:Agent`        | An entity responsible for producing the dataset. | Resources of type foaf:Agent are recommended as values for this property. See also 	DCAT 3 - 6.12 Class: Organization/Person | 
| [dcat:publisher](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_publisher) | `dcat:Resource`   | `foaf:Agent`        | This property refers to an entity (organisation) responsible for making the Dataset available. | 
 |
| [prov:qualifiedAttribution](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_qualifiedAttribution) | `dcat:Resource`   | `prov:Attribution`  | This property refers to a link to an Agent having some form of responsibility for the dataset | Used to link to an Agent where the nature of the relationship is known but does not match one of the standard [ DCTERMS ] properties ( dcterms:creator , dcterms:publisher ). Use dcat:hadRole on the prov:Attribution to capture the responsibility of the Agent with respect to the Resource. See DCAT 3 - 15.1 Relationships between datasets and agents for usage examples.

#WIKIDATA oder sie müssen einfach den Type angeben, wie bei dcat.ap.de siehe https://www.dcat-ap.de/def/dcatde/3.0/spec/#datensatz-herausgeber


### Usage Notes

#### dcat:creator
An entity responsible for producing the dataset (provider of the technical components), organisation or company. | Resources of type foaf:Agent are recommended as values for this property. See also 	DCAT 3 - 6.12 Class: Organization/Person. 
Controlled Vocabularies to be used:
* If from the public sector, use the same CV as dcat:publisher
* For swiss companies, use the corresponding Zefix entry [https://register.ld.admin.ch/zefix/company/122015](https://register.ld.admin.ch/zefix/company/122015), you can find the EHRA-ID of organisations on http://zefix.ch
* Fallback: We recommend using the correspondend entry in Wikidata as CV, it is straight forward to add a missing entity to Wikidata.

Example
```
<https://ld.admin.ch/office/III.1.4> a <http://xmlns.com/foaf/0.1/Organization>, <http://xmlns.com/foaf/0.1/Agent> ;
	<http://xmlns.com/foaf/0.1/name> "Staatssekretariat für Migration"@de, "Segreteria di Stato della migrazione"@it, "Secrétariat d’Etat aux migrations"@fr, "Secretariat da stadi per migraziun"@rm .
```

#### dcat:publisher

The organisation MUST be the one that has published the dataset (in the legal sense, not the technical sense), i.e. that has decided to grant rights of use to third parties. It is favorable to use a more specific publisher, i.e. "Office of Cyberadministration of Lucern" over "Canton of Lucern".

Controlled Vocabularies to be used:
* CH Federal Level:
  * Vocabulary for departments based on [RVOV](https://www.fedlex.admin.ch/eli/cc/1999/170/de)  <a href="https://ld.admin.ch/department/V">https://ld.admin.ch/department/V</a> (I-V) and for offices <a href="https://ld.admin.ch/office/V.1.6</a>./li>
  * Fallback: We recommend using the correspondend entry in Wikidata as CV: for example Entry of the <a href="[https://www.wikidata.org/entity/Q1326584](http://www.wikidata.org/entity/Q1326584)">Federal Electricity Commission</a>.
* Cantonal or Municipal Level:
  * Usage of the published foaf:Agent by the local agency if available.
  * Fallback: We recommend using the correspondend entry in Wikidata as CV, it is straight forward to add a missing entity to Wikidata.
 
Note: Use the Concept URI for Wikidata Entries http://www.wikidata.org/**entity**/Q1326584 not http://www.wikidata.org//wiki/Q1326584


 
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
