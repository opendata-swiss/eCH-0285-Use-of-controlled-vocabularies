# License

## Context
### DCAT - Version 3
| **Predicate** | **Domain** | **Range** | **Description** |
|---------------|------------|-----------|-----------------|
| [dcterms:license](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#license) | `dcat:Resource` | `dcterms:LicenseDocument` | A legal document under which the distribution is made available. |
| [dcterms:license](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#license) | `dcat:Distribution` | `dcterms:LicenseDocument` | A legal document under which the distribution is made available. |

In **DCAT-AP CH Version 2**, `dcterms:license` MUST use the [VOCAB-CH-LICENSE](https://dcat-ap.ch/vocabulary/licenses/20240716.html) Controlled Vocabulary.

## Usage Note

Information about licenses SHOULD be provided on the level of Distribution.
Information about licenses and rights MAY be provided for the ~~dcat:Resource~~ DataService or Catalog.

Providing license or rights information for a DataService (or Catalog) that is different from information provided for a Distribution of that ~~dcat:Resource~~ DataService (or Catalog) SHOULD be avoided as this can create legal conflicts.

~~See also guidance at [9. License and rights statements](https://www.w3.org/TR/vocab-dcat-3/#license-rights).~~

We RECOMMEND using the [VOCAB-CH-LICENSE](https://dcat-ap.ch/vocabulary/licenses/20240716.html]) or the [SPDX License List](https://spdx.org/licenses/) controlled vocabulary.


## Decisions
*What* has been decided and *why*?


## Discussion
Topics to discuss or remarks. From most to least important.

1. Recommend the Vocabulary instead of forcing it. [VOCAB-CH-LICENSE](https://dcat-ap.ch/vocabulary/licenses/20240716.html])
1. Add [SPDX License List](https://spdx.org/licenses/) to the recommended list of codes.
