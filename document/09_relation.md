# Qualified Relation / Relation to Datasets; (liber)

## Context
  
| **Predicate**    | **Domain**        | **Range**           | **Description**  |
|------------------|------------------|---------------------|------------------|
| [dcat:qualifiedRelation](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#dataset-qualified-relation) | `dcat:Dataset`  | `dcat:Relationship`  | Used to link to another resource where the nature of the relationship is known but does not match one of the standard properties. |
| [dct:relation](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#dataset-related-resource) | `dcat:Resource` | `rdfs:Resource` | A resource with an unspecified relationship to the cataloged resource. |


  - **opendata.swiss - Qualified relation:** Only possible to use the relationship `"related"` associated only with internal dataset on opendata.swiss platform (only a link, not a vocabulary).  
  - **I14Y - Qualified relation:** Three possible relationships (`owl:sameAs`, `related`, and `original`; taken from IANA vocabulary).  
  - **opendata.swiss - Relation:** Related information  


# Usage Note

Please use one of the following vocabularies:
  - [DataCite](https://datacite-metadata-schema.readthedocs.io/en/4.6/properties/relateditem/#b-relationtype) metadata schema 
  - DS_AssociationTypeCodes values from [ISO-19115-1](https://standards.iso.org/iso/19115/resources/Codelists/gml/DS_AssociationTypeCode.xml)
  - DS_AssociationTypeCodes values from [ISO-19115-1](https://standards.iso.org/iso/19115/resources/Codelists/gml/DS_AssociationTypeCode.xml) extended in the Swiss version (CHE_DS_AssociationTypeCode) with the values: `isTemporalStateOf`, `isDescriptionOf`, and `isDescribedBy`.

## Examples 

```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix ex: <http://example.org/> .

  ex:Example123
  a dcat:Dataset ;
    dcat:qualifiedRelation [
    a dcat:Relationship ;
    dct:relation <http://example.org/Original123> ;
    dcat:hadRole <http://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/relationType/#isvariantformof>
  ] .


  ex:Test543L
  a dcat:Dataset ;
  dcat:qualifiedRelation [
    a dcat:Relationship ;
    dct:relation <http://dcat.example.org/Test543R> ;
    dcat:hadRole <urn:example:isotc211/DS_AssociationTypeCode/stereoMate>
  ] .
```

## Decisions (and Reasoning)
1. We recommend three specific vocabularies to enhance consistency:
      - DataCite metadata schema
      - ISO 19115-1 DS_AssociationTypeCodes
      - CHE_DS_AssociationTypeCode (Swiss extension)
2. We opted against recommending the [IANA Registry of Link Relations](https://www.iana.org/assignments/link-relations/link-relations.xhtml) and [MARC relators](https://id.loc.gov/vocabulary/relators.html), even if they are suggested by DCAT 3, because they don't cover the semantic needs of this property. 

## Discussion
- [DCAT Qualified Forms](https://www.w3.org/TR/vocab-dcat/#qualified-forms)
- For `qualifiedRelation`, **DCAT 3** suggests using:
  - **DS_AssociationTypeCodes** values from **[ISO-19115-1]**  
    [ISO-19115-1 Codelist](https://standards.iso.org/iso/19115/resources/Codelists/gml/DS_AssociationTypeCode.xml)  
  - **IANA Registry of Link Relations**  
    [IANA Relations](https://www.iana.org/assignments/link-relations/link-relations.xhtml)  
  - **MARC Relators**  
    [MARC Relators](https://id.loc.gov/vocabulary/relators.html)  
  - **The [DataCite] metadata schema**  
    [DataCite Schema](https://datacite-metadata-schema.readthedocs.io/en/4.6/properties/relateditem/#b-relationtype)  

- **Recommendation:** Do **not** use MARC relators for `qualifiedRelation` (it is more suitable for `qualifiedAttribution`, not `qualifiedRelation`).  

- **For Geometadata**, the following **Codelist** will be implemented with `eCH-0271: ISO19115. CHE_DS_AssociationTypeCode`:  
  - `crossReference`
  - `largerWorkCitation`
  - `partOfSeamlessDatabase`
  - `stereoMate`
  - `isComposedOf`
  - `collectiveTitle`
  - `series`
  - `dependency`
  - `revisionOf`
  - `isTemporalStateOf`
  - `isDescriptionOf`
  - `isDescribedBy`

---

## Change log (vs. Version 2)
- Introduced three recommended vocabularies. 
- Added an example showcasing the suggested vocabularies.

