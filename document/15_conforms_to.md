# Conforms To ( odi / lmi / hut )

# dct:conformsTo

## Context

RDF Property [dcterms:conformsTo](https://purl.org/dc/terms/conformsTo)
  * Domain: `dcat:Dataset` 
  * Range: [dcterms:Standard](http://purl.org/dc/terms/Standard)
  * Description: The standard or schema this dataset conforms to.

## Usage Note 
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
 
## Examples
* Concrete examples with the use of the full URIs.
* Examples in Turtle.
* Per case at least one example.

0. Use an existing standard:

```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.org/dataset/1> a dcat:Dataset ;
    dcterms:conformsTo <http://example.org/csv/my-standard> .

# Reference standard / specification
<http://example.org/csv/my-standard> a dcterms:Standard ;
  dcterms:title "Commission Regulation (EU) No 1089/2010 of 23 November 2010 implementing Directive 2007/2/EC of the European Parliament and of the Council as regards interoperability of spatial data sets and services"@en ;
  dcterms:issued "2010-11-23"^^xsd:date .
```


0. Define fields of a CSV:

```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.org/dataset/1> a dcat:Dataset ;
     dct:conformsTo <http://www.opengis.net/def/crs/EPSG/0/2056> #LV95 .
```

## Decisions (and Reasoning)

* Which decisions, pro- / contra were taken, and why

## Change log (vs. Version dcat-ch V2)
* What change, and which advantage it brings.

## Discussion
* data schema (also interaction with qualifiedRelation)
