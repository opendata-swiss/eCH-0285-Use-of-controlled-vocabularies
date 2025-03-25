# Licences: ( flof / lmi / liber )

## Context
RDF Property [dcterms:license](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_license)
  * Domain: `dcat:Resource`, `dcat:Distribution` 
  * Range: [dcterms:LicenseDocument](http://purl.org/dc/terms/LicenseDocument)
  * Description: A legal document under which the resource is made available



## Usage Note
* Licences *should* be provided for each [Distribution](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Distribution).
* Information about licenses *may* be provided for the [CataloguedResource](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#CataloguedResource). It is highly recommended that the CataloguedResource and its contained Distributions share the same license to avoid legal conflics.
* DCAT-AP CH recommends the usage of [VOCAB-CH-LICENSE](https://www.dcat-ap.ch/vocabulary/licenses/20240716.html) or [SPDX License List](https://spdx.org/licenses/) as licensing options.

* Multiple licenses may be listed if applicable.

## Discussion:

* Opendata.swiss only uses the [VOCAB-CH-LICENSE](https://www.dcat-ap.ch/vocabulary/licenses/20240716.html). This information should be provided by opendata.swiss. Information about opendata.swiss should not be displayed in the usage note of dcterms:license, because DCAT-AP CH and opendata.swiss are two separate entities. The dependency goes only one way: ( opendata.swiss → use → DCAT-AP CH )

* **To review**: Michèle Spichtig & Michael Luggen
  * Should we allow the usage of SPDX ?
  * Should the use of VOCAB_CH_LICENSE be recommended/mandatory?

  Note: Michael said the URI on the SPDX website is missing something. [uri-example](https://prateekvjoshi.com/wp-content/uploads/2014/02/uri-vs-url-vs-urn.jpg)

- **Proposal:** The usage of DCAT-AP CH license vocabulary should be *recommended* instead of *mandatory*.  
  - **Why?** Many 3rd parties may use our standard. They will need to use different licenses. 
  - **counter-argument:** If DCAT-AP CH is used only with opendata.swiss, or if it is agreed that all institution of the Swiss Confederacy will be limited DCAT-AP CH, it will make the license managment much simpler.

- **Proposal:** We should add the SPDX License List to the recommended list of vocabularies.  (see above-proposal)
  - **Why?** This is a list of commonly used licenses used by the majority of open projects. 

- Michèle gave an input from the side of opendata.swiss
  - Shall we use it still? Or rework it? [DCAT-AP CH Vocabulary](https://dcat-ap.ch/vocabulary/licenses/20210623.html)
  - Instead of domain `dcat-ap.ch`.
