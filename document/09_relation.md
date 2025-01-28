# Qualified Relation / Relation to Datasets; (liber)

## Context
- **dcat:qualifiedRelation**  
  - **Domain:** `dcat:Resource`  
  - **Range:** `dcat:Relationship`  
  - **Description:** Used to link to another resource where the nature of the relationship is **known** but **does not** match one of the standard properties.  
  - **opendata.swiss:** Only possible to use the relationship `"related"` associated only with internal dataset on opendata.swiss platform (only a link, not a vocabulary).  
  - **I14Y:** Three possible relationships (`owl:sameAs`, `related`, and `original`; taken from IANA vocabulary).  

- **dct:relation**  
  - **Domain:** `dcat:Resource`  
  - **Range:** `rdfs:Resource`  
  - **Description:** A resource with an unspecified relationship to the cataloged resource.  
  - `"dcterms:relation SHOULD be used where the nature of the relationship between a cataloged resource and related resources is not known"`  
  - [Reference](https://www.w3.org/TR/vocab-dcat/#Property:resource_qualified_relation)  
  - **opendata.swiss:** Related information  

- **dcatap:applicableLegislation**  
  - **Domain:** `rdfs:Resource`  
  - **Range:** `eli:LegalResource`  
  - **Description:** The legislation that mandates the creation or management of the **Distribution**.  

---

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

## Usage Note
Please use one of the following vocabularies:
- **The [DataCite] metadata schema**  
  [DataCite Schema](https://datacite-metadata-schema.readthedocs.io/en/4.6/properties/relateditem/#b-relationtype)  
- **DS_AssociationTypeCodes values from [ISO-19115-1]**  
  [ISO-19115-1 Codelist](https://standards.iso.org/iso/19115/resources/Codelists/gml/DS_AssociationTypeCode.xml)  
- **Swiss version `CHE_DS_AssociationTypeCode`**  
  - With three additional codes:  
    - `isTemporalStateOf`
    - `isDescriptionOf`
    - `isDescribedBy`
