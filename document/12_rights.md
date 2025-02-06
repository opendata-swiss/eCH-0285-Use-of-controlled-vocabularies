# Rights; (lien/lmi)


## Context:
 * Domain: dcat:Catalog and dcat:Distribution
 * There is also Licence, which is specific for Licencing 
 * There is also Access Rights: Which is only stating if the dataset in the style of "open"/"closed"/"restricted". See (publications.europa.eu/resource/authority/access-right).
 * This is not in the meaning of a legal "applicable legislation". (False friend, right != Recht).
 * DCTERMS rights definition: "Typically, rights information includes a statement about various property rights associated with the resource, including intellectual property rights. Recommended practice is to refer to a rights statement with a URI. If this is not possible or feasible, a literal value (name, label, or short text) may be provided." https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/rights/ 
 * DCTERMS RightsStatment definition: "A statement about the intellectual property rights (IPR) held in or over a resource, a legal document giving official permission to do something with a resource, or a statement about access rights." https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/RightsStatement/ 

## Usage Note:
 * First use dct:licence and dct:accessRights, only use dct:rights if you want to specificy more specific information about the right situation of this dataset.
 * Add a link to the legal text, which provides the base for this dataset by using applicableLegislation.
 * dct:rights add information about the legal framework. Recommended to point to a rights statement as an URI. Only use ODRS  (http://schema.theodi.org/odrs/).
