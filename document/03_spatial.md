# Spatial Concerns (dip/odi)

## Context
- RDF Property **dct:spatial**  
  - **Domain:** `dcat:Catalogue`, `dcat:Dataset`, `dcat:DatasetSeries`  
  - **Range:** `dcat:Location`
  - **Description:** The geographical area covered by a resource
    
- RDF Class **dct:Location**  
  - **Description:** A spatial region or a named place. Specific to this class are the properties `locn:geometry`, `dcat:bbox`, `dcat:centroid`

- RDF Property **locn:geometry**  
  - **Range:** `locn:Geometry`
  - **Description:** Associates a resource with a corresponding geometry

- RDF Property **dcat:bbox**  
  - **Range:** `geosparql:wktLiteral`
  - **Description:** The geographical bounding box of a resource

- RDF Property **dcat:centroid**  
  - **Range:** `geosparql:wktLiteral`
  - **Description:** The geographical center of a resource

## Usage Note
### dct:spatial

* This property may be indicated using an IRI reference or may be encoded as an instance of `dct:Location`
* CV to be used for IRI reference: LINDAS resources SHOULD be used. Whenever a particular location in not available as LINDAS resource, then the EU Vocabularies Named Authority Lists MAY be used: if the location is not in one of the mentioned EU Vocabularies, then Geonames URIs MAY be used
* For the encoding as instance of `dct:Location` see the class Location

#### Examples
##### Switzerlan and Liechtenstein - LINDAS
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> .

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;
   dct:spatial <https://ld.admin.ch/country/CHE>,  <https://ld.admin.ch/country/LIE>.
```
##### The Cantons Basel-Stadt and Basel-Landschaft - LINDAS
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> .

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;
   dct:spatial <https://ld.admin.ch/canton/12>,  <https://ld.admin.ch/canton/13>.
```
##### Switzerland and Deutschland- LINDAS and EU Vocabulary
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> .

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;
   dct:spatial <https://ld.admin.ch/country/CHE>,  <https://publications.europa.eu/resource/authority/country/DEU>.
```

### dct:Location
The class `dct:Location` enables to encode the geometry of the geographical area covered by a resource.
* For an extensive geometry (e.g. a set of coordinates), the property `locn:geometry` SHOULD be used: the geometry can be encoded as a `geosparql:wktLiteral` or represented by a class as `geosparql:Geometry`
* For the representation by a class as `geosparql:Geometry` the resources of the Linked Data Service of the Federal Spatial Data Infrastructure MAY be used
* For a geographical bounding box, the property dcat:bbox SHOULD be used with range `geosparql:wktLiteral`
* For the geographical center of a spatial region, the property dcat:centroid SHOULD be used with range `geosparql:wktLiteral`
* Whenever a coordinate reference system is not specified, the coordinates are assumed to be longitude and latitude expressed in decimal degrees according to EPSG:4326 (http://www.opengis.net/def/crs/EPSG/0/4326)

#### Examples
##### Geometry as polygon - EPSG:4326
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> . 
@prefix locn: <http://www.w3.org/ns/locn#> . 
@prefix geosparql: <http://www.opengis.net/ont/geosparql#> .  

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;  
   dct:spatial [
      a dct:Location ; 
   locn:geometry """POLYGON ((7.451387 46.928685, 7.451231 46.928678, 7.450437 46.927861, 7.450888 46.927539, 7.451398 46.927282, 7.452337 46.928238, 7.451387 46.928685))"""^^geosparql:wktLiteral ; 
] .
```
##### Geometry as polygon in swiss coordinates - EPSG:2056
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> . 
@prefix locn: <http://www.w3.org/ns/locn#> . 
@prefix geosparql: <http://www.opengis.net/ont/geosparql#> .  

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;  
   dct:spatial [
      a dct:Location ; 
   locn:geometry """<http://www.opengis.net/def/crs/EPSG/0/2056> POLYGON ((2600969.758793 1197513.132435, 2600959.031118 1197512.780712, 2600896.919378 1197415.416299, 2600939.877991 1197372.121926, 2600969.439038 1197351.961561, 2601039.576595 1197465.425479, 2600969.758793 1197513.132435))"""^^geosparql:wktLiteral  ;
] .
```
##### Geometry represented by a class as `geosparql:Geometry`
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> . 
@prefix locn: <http://www.w3.org/ns/locn#> . 
@prefix geosparql: <http://www.opengis.net/ont/geosparql#> .  

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;  
   dct:spatial [
      a dct:Location ; 
   locn:geometry <https://geo.ld.admin.ch/boundaries/canton/geometry-g1/2:2024> ;
] .
```
##### Bounding Box - EPSG:4326
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> . 
@prefix geosparql: <http://www.opengis.net/ont/geosparql#> .  

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;  
   dct:spatial [
      a dct:Location ; 
   dcat:bbox """POLYGON((7.45047 46.92726, 7.452359 46.92726, 7.452359 46.92874, 7.45047 46.92874, 7.45047 46.92726))"""^^geosparql:wktLiteral ;
  ] .
```
##### Bounding Box in swiss coordinates - EPSG:2056
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> . 
@prefix geosparql: <http://www.opengis.net/ont/geosparql#> .  

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;  
   dct:spatial [
      a dct:Location ; 
   dcat:bbox """<http://www.opengis.net/def/crs/EPSG/0/2056> POLYGON((2600901.5155893597 1197351.6682247864, 2601045.3813676247 1197351.6899351375, 2601045.354556491 1197516.221996089, 2600901.4927423815 1197516.2002863828, 2600901.5155893597 1197351.6682247864))"""^^geosparql:wktLiteral ;
  ] ;
```
##### Centroid - EPSG:4326
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> . 
@prefix geosparql: <http://www.opengis.net/ont/geosparql#> .  

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;  
   dct:spatial [
      a dct:Location ; 
   dcat:centroid "POINT(7.451842 46.928314)"^^geosparql:wktLiteral ;
] .
```
##### Centroid in swiss coordinates - EPSG:2056
```
@prefix dcat: <http://www.w3.org/ns/dcat#> . 
@prefix dct: <http://purl.org/dc/terms/> . 
@prefix geosparql: <http://www.opengis.net/ont/geosparql#> .  

<https://ckan.opendata.swiss/dataset/aDataset> a dcat:Dataset ;  
   dct:spatial [
      a dct:Location ; 
   dcat:centroid "<http://www.opengis.net/def/crs/EPSG/0/2056> POINT(2601005.984787 1197468.845944)"^^geosparql:wktLiteral ;
] .
```

## Decisions (and Reasoning)

## Discussion

* Spatial / Geographic
     * Use-Case 
     * Search
* mit semantischen Konzepten
* auf Karte
          * Übersicht auf Karte anzeigen
* Harvesting from EU
* Geometry vs Location Vocabulary
* Beides erlauben ?
* Geometrien ausschliessen ?
* Bounding Box ?
* Problematik mit verbunden Location Regions?
* Define a URI Set for Swiss Boundaries (Municipality, District, Canton)
  * Identity (which points the boundaries)
  * Boundaries
* Problematik CH?
  * Use EU-Vocabularity, Swisstopo
