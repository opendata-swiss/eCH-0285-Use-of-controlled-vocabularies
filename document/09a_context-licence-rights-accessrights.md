# Overview on the related topics rights, licences, access rights ( liber / flof )

## Context

Originally, DCAT v3 also had a need to explain in-deptht the nuances of licencing and right management. They created a chapter specifically to explain it.

DCAT: https://www.w3.org/TR/vocab-dcat-3/#license-rights

DCAT-AP: https://semiceu.github.io/DCAT-AP/releases/3.0.0/#legal-information

## License and rights statements

*This section is non-normative.*

Selecting the right way to express conditions for access to and re-use of resources can be complex. Implementers should always seek legal advice before deciding which conditions apply to the resource being described.

This specification distinguishes three main situations: one where a statement is associated with a resource that is explicitly declared as a 'license'; a second, where the statement is associated with a resource denoting only access rights; a third, covering all the other cases - i.e., statements not concerning licensing conditions and/or access rights (e.g., copyright statements).

> NOTE
> 
> The provision of licensing conditions and access rights complies with the Best Practices 4 ("[Provide data license information](https://www.w3.org/TR/dwbp/#licenses)") and 22 ("[Provide an explanation for data that is not available](https://www.w3.org/TR/dwbp/#DataUnavailabilityReference)"), respectively, from [[DWBP](https://www.w3.org/TR/vocab-dcat-3/#bib-dwbp)].

To address these scenarios, it is recommended to use the property dcterms:rights, and its sub-properties dcterms:license and dcterms:accessRights. More precisely:

1. use [dcterms:license](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/license) to refer to licenses;

    > NOTE
    > 
    > For interoperability, it is recommended to use canonical IRIs of well-known *open* licenses such as [VOCAB-CH-LICENSE](https://www.dcat-ap.ch/vocabulary/licenses/20240716.html) and [SPDX License List](https://spdx.org/licenses/).


2. use [dcterms:accessRights](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/accessRights) to express statements concerning only access rights (e.g., whether data can be accessed by anyone or just by authorized parties);

    > NOTE
    >
    > Access rights can also be expressed as code lists / taxonomies. Examples include the access rights code list [[EUV-AR](http://publications.europa.eu/resource/authority/access-right)] used in [DCAT-AP CH] and the [Eprints Access Rights Vocabulary Encoding Scheme](http://purl.org/eprint/accessRights/).


3. use [dcterms:rights](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/rights) for all the other types of rights statements - those which are not covered by dcterms:license and dcterms:accessRights, such as copyright statements.

    > NOTE
    > 
    > A more sophisticated approach to express rights, based on and extending [[DCTERMS](https://www.w3.org/TR/vocab-dcat-3/#bib-dcterms)], is provided by the Open Data Rights Statement Vocabulary [[ODRS](https://www.w3.org/TR/vocab-dcat-3/#bib-odrs)], which defines properties for specifying, among others, copyright statements and copyright notices.


> EXAMPLE 19: License, access rights, and copyright statement
>
> The following example is about a dataset publicly available (with no access restriction) and whose distribution is released by using a standard license - namely, XXXXX. Access rights are specified by using the YYYYY code list. Property dcterms:rights is used for ...
>
> 
> ```
> ex:ds7890 a dcat:Dataset ;
> # other dataset properties...
>  dcterms:accessRights 
>    <http://publications.europa.eu/resource/authority/access-right/PUBLIC> ;
>  dcterms:rights [ YYYYYYY ] ;
>  dcat:distribution [ a dcat:Distribution ;
>    # other distribution properties...
>    dcterms:license XXXXXXX>  ] ;
>.
> ```
>





## Decisions (and Reasoning)
None yet ...

## Discussion

### Mandatory vs Recommended Vocabulary

The usage of VOCAB-CH-LICENSE is still *in discussion*. We must not forget to update this comment once a final decision on `10_licences.md` is given.

Related text:


1. use [dcterms:license](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/license) to refer to licenses;

> NOTE
> 
> For interoperability, it is recommended to use canonical IRIs of well-known *open* licenses such as [VOCAB-CH-LICENSE](https://www.dcat-ap.ch/vocabulary/licenses/20240716.html) and [SPDX License List](https://spdx.org/licenses/).
---

### Link to DCAT-AP CH

Do not forget to add the link to [DCAT-AP CH] documentation once we have an official and final URL for it.

Related text:

2. use [dcterms:accessRights](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#http://purl.org/dc/terms/accessRights) to express statements concerning only access rights (e.g., whether data can be accessed by anyone or just by authorized parties);

> NOTE
>
> Access rights can also be expressed as code lists / taxonomies. Examples include the access rights code list [[EUV-AR](http://publications.europa.eu/resource/authority/access-right)] used in [DCAT-AP CH] and the [Eprints Access Rights Vocabulary Encoding Scheme](http://purl.org/eprint/accessRights/).
---

### Complete or remove example

EXAMPLE 19 must be either completed or removed.

---
