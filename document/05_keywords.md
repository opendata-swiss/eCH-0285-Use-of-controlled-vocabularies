# Keywords (aka Tags) (lmi/odi)

## Context

## Usage Note



Keywords primarily serve to support **search functionality** on Data Catalogs. Using more keywords is preferable to using fewer. Keywords should be selected from the perspective of those conducting searche. Consider, that keywords which are obvious for you as a publisher might be usefull for the search. E.g. add *environmental monitoring* (http://www.wikidata.org/entity/Q1749732) if you as a data publisher are an Environmental Monitoring Agency.

Both controlled vocabularies and literals are allowed, but controlled vocabularies SHOULD be used.

* Priority cascade of how adding Keywords:
  1. use Termdat: Look for a term on termdat.ch. E.g. *Grünabfälle*, take the entry ID (51810), and build the Concept URI by adding the ID to *https://register.ld.admin.ch/termdat/* (e.g. https://register.ld.admin.ch/termdat/51810)
  2. use GEMET (especially in a Geo Context): Look for a term on http://www.eionet.europa.eu/gemet/. Use the concept URL, as statet on the *bottom of the page of a concept* (e.g. http://www.eionet.europa.eu/gemet/concept/428)
  3. If there are no matching Concepts neither in Termdat nor GEMET, look in Wikidata (top right search). Use the Concept URI (entry in the left side). (e.g. http://www.wikidata.org/entity/Q1749732, do not copy the URL <s>https://www.wikidata.org/**wiki**/Q1749732</s>
  4. If you can't find a fitting concept, you can always add your own concept to Wikidata.
  5. Finally as a last resort, you can add a Keyword as a Literal. 


Example 25: Usage of dcat:keyword for dcat:Dataset
```
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .

<https://swisstopo/opendata/dataset/1234>
  a dcat:Dataset ;
  dcat:keyword <https://register.ld.admin.ch/termdat/215878>, #hochwasser
               <https://register.ld.admin.ch/termdat/216331>, #ereigniskataster
               <https://register.ld.admin.ch/termdat/502116>, #lawine
               <https://register.ld.admin.ch/termdat/216219>, #murgang
               <https://register.ld.admin.ch/termdat/216292>. #naturereignis
```

## Decisions (and Reasoning)

## DCAT-AP-CH
* Anpassen der Range für dcat:keyword

## Discussion



* Keyword / Topics (Specific, Local) (+ dcat:keyword, sdo:keywords, foaf:primaryTopic ?)
  * Stefan / Michael / Pasquale

  * Problematik des Range von dcat:keyword ist rdf:Literal
       * Drop the range of dcat:keyword · Issue #1585 · w3c/dxwg https://github.com/w3c/dxwg
  * Vorschlag: Wir erlauben beides rdf:Literal und skos:Concept / schema:DefinedTerm (Data Catalog Vocabulary (DCAT) - Version 3)
  * Bezüglich der Problematik der Mehrsprachigkeit nötig für den CH Context.
  * CV haben Vorrang und SHULD be used über Literals (geplant auf MUST be used in 2028) / (opendata.swiss zeigt in Zukunft nur CV an)
  * Auswahl Kaskadiert (von spezifisch (Schweiz -> Welt) zu generisch)
    * Termdat (Vorbehalte gegenüber Termdat aus Kantonen)
    * (GeoCat Keywords (Subset Termdat?) -> Pasquale klärt ab)
    * Gemet: http://www.eionet.europa.eu/gemet/concept/100 -> administrative body
    * Wikidata (wenn kein Begriff gefunden wurde)
  
