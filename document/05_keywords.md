# Keywords (aka Tags) (lmi/odi)

## Context

## Usage Note

* Suchunterstützend
* Mehr besser als, wenige.
* Aus der Perspektive der Suchenden (auch für publizierende klare, offensichtliche Keywords anfügen)
* CV und Literals erlaubt, vorrang ganz klar controlled vocabularies.
* 

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
  
