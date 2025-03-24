# Licences: ( flof / lmi / liber )

## Context
RDF Property [dcterms:license](https://www.w3.org/TR/vocab-dcat-3/#Property:resource_license)
  * Domain: `dcat:Catalogue`, `dcat:DataService`, `dcat:Distribution` 
  * Range: [dcterms:LicenseDocument](http://purl.org/dc/terms/LicenseDocument)
  * Description: A legal document under which the resource is made available



## Usage Note a
* Licences *should* be provided for each [Distribution](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Distribution).
* Licenses *may* also be specified for a [DataService](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#DataService) or [Catalogue](https://semiceu.github.io/DCAT-AP/releases/3.0.0/#Catalogue). In such cases, it is highly recommended that the Catalog/DataService and its contained Distributions share the same license to avoid legal conflics.
* The [VOCAB-CH-LICENSE](https://www.dcat-ap.ch/vocabulary/licenses/20240716.html) controlled vocabulary is mandatory (MUST) for all datasets produced by administrative units of the Swiss Confederacy on. However, both the [VOCAB-CH-LICENSE](https://www.dcat-ap.ch/vocabulary/licenses/20240716.html) and the [SPDX License List](https://spdx.org/licenses/) are valid licensing options in DCAT-AP CH.

* Multiple licenses may be listed if applicable.

## Discussion:

* **To review**: Michèle Spichtig & Michael Luggen
  * Do we allow the usage of SPDX ?
  * Do we keep the license vocabulary VOCAB_CH_LICENSE mandatory?

  Note: Michael said the URI on the SPDX website is missing something. [uri-example](https://prateekvjoshi.com/wp-content/uploads/2014/02/uri-vs-url-vs-urn.jpg)

- **Proposal:** The usage of DCAT-AP CH license vocabulary should be *recommended* instead of *mandatory*.  
  - **Why?** Many 3rd parties may use our standard. They will need to use different licenses. 
  - **counter-argument:** If DCAT-AP CH is used only with opendata.swiss, or if it is agreed that all institution of the Swiss Confederacy will be limited DCAT-AP CH, it will make the license managment much simpler.

- **Proposal:** We should add the SPDX License List to the recommended list of vocabularies.  (see above-proposal)
  - **Why?** This is a list of commonly used licenses used by the majority of open projects. 
  
- Examples should be added for other licences, especially SPDX.

- Michèle gave an input from the side of opendata.swiss
  - Shall we use it still? Or rework it? [DCAT-AP CH Vocabulary](https://dcat-ap.ch/vocabulary/licenses/20210623.html)
  - Instead of domain `dcat-ap.ch`.
