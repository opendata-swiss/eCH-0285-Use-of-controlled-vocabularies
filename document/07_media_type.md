# Formate/Mediatypes/Packaging Format (Distributions) (odi / hut)

# dct:format

## Context

RDF Property [dcterms:format](http://purl.org/dc/terms/format)
  * Domain: `dcat:Distribution` 
  * Range: [dcterms:MediaTypeOrExtent](http://purl.org/dc/terms/MediaTypeOrExtent)
  * Description: The format of the distribution.


## Usage Note

* This property refers to the file format of the Distribution.
* CV to be used: [[VOCAB-EU-FILE-TYPE]](http://publications.europa.eu/resource/authority/file-type)
* If a format is not available in the CV then: a) media type ([[IANA-MEDIA-TYPES]](https://www.iana.org/assignments/media-types/)) should be used, see also dcat:mediaType property  b) If necessary, a discussion to evaluate the adoption within the EU should be launched (Contact point: [[VOCAB-EU-OP-CONTACT]](https://op.europa.eu/en/web/about-us/contact-us)).

## Decisions (and Reasoning)

- no change for the CV is needed, because it already reflects a good practice.

## Change log (vs. Version dcat-ch V2)

- minor change to link to the dcat:mediaType property


# dcat:mediaType

## Context

RDF Property [dcat:mediaType](https://www.w3.org/ns/dcat#mediaType)
  * Domain: `dcat:Distribution` 
  * Range: [dcterms:MediaType](http://purl.org/dc/terms/MediaType)
  * Description: The media type of the distribution.


## Usage Note

* This property refers to the media type of the Distribution as defined in the official register of media types managed by IANA.
* The value of the element "dcat:mediaType" *must* correspond to a MIME type according to IANA: [[IANA-MEDIA-TYPES]](https://www.iana.org/assignments/media-types/).

## Decisions (and Reasoning)

- no change for the CV is needed, because it already reflects a good practice.

## Change log (vs. Version dcat-ch V2)

- no change to V2

# dcat:packageFormat

## Context

RDF Property [dcat:packageFormat](https://www.w3.org/TR/vocab-dcat/#Property:distribution_packaging_format)
  * Domain: `dcat:Distribution` 
  * Range: [dcterms:MediaType](http://purl.org/dc/terms/MediaType)
  * Description: The format of the file in which one or more data files are grouped together.


## Usage Note

* This property refers to the format of the file in which one or more data files are grouped together, e.g. to enable a set of related files to be downloaded together.
* It *should* correspond to a MIME type according to IANA: [[IANA-MEDIA-TYPES]](https://www.iana.org/assignments/media-types/).

## Decisions (and Reasoning)

- no change for the CV is needed, because it already reflects a good practice.

## Change log (vs. Version dcat-ch V2)

- Link to IANA

# Discussion

  (Stefan / Tania)

Generell: die Usage Note so beibehalten und die Kaskade vo CVs wie aktuell in DCAT-AP CH 2 vorgeschlaten beibehalten.

* [dct:format](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#distribution-format): CV so beibehalten ([VOCAB-EU-FILE-TYPE](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#bib-vocab-eu-file-type)), und falls nicht verfügbar IANA ([IANA-MEDIA-TYPES](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#bib-iana-media-types)), Vorschlag: so beibehalten
* [dcat:mediaType](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#distribution-media-type): IANA, Vorschlag: so beibehalten
* [dcat:packageFormat](https://www.dcat-ap.ch/releases/2.0/dcat-ap-ch.html#distribution-packaging-format): IANA, Vorschlag: so beibehalten

* OpenData.swiss -> kann bei EU Anfragen für Eintrag.
* I14Y -> für zusätzliche nicht in IANA vorhanden?
* Was machen wenn weder EU-VOCAB noch IANA-MEDIA-TYPE da ist. Geo spezifische Dinge?
