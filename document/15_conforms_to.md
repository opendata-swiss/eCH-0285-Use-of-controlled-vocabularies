# Conforms To ( odi / lmi / hut / dip )

# dct:conformsTo

## Context

RDF Property [dcterms:conformsTo](https://purl.org/dc/terms/conformsTo)
  * Domain: `dcat:Dataset` 
  * Range: [dcterms:Standard](http://purl.org/dc/terms/Standard)
  * Description: The standard or schema this dataset conforms to.

## Usage Note 
* The main idea of this property is to point to a technical description (schema, ontology, data structure description) which allows to automatically confirm the form of the dataset at hand. 
* Ideally the reference is a description in either
 * XSD
 * JSON-SCHEMA
 * RDFS / OWL / SHACL


## Class definition

dcterm:standard
 * dcterm:title "CSVW Abfallkalender JSON"
 * dcterm:form csvw
 * dcterm:target https://metaodi.ch/abfallkalender.json

dcterm:standard
 * dcterm:title "Politische Geschäfte XSD Version 2.0"
 * dcterm:form xsd
 * dcterm:target https://ech.ch/blabla/poge2.0.xsd


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

## Discussion
* Link also zu Geo Modellen (Interlis)

## Change log (vs. Version dcat-ch V2)
* What change, and which advantage it brings.

## Discussion
* data schema (also interaction with qualifiedRelation)
