# General Remarks and Guidelines for Controlled Vocabularies

## Best practice in regard to Controled Vocabularies

## Rules regarding Controlled Vocabularies (lmi)
* The main goal is to use the same Identifiers as others for the same things, so in doubt it is useful, to copy from other examples.
* If a controlled vocabulary is missing an entry. First always try to open a question at the authority of the controlled vocabulary. Only if you get no answer in reasonable time, or it is clear that the entry only makes sense in the Context of Switzerland, contact the authors of this standard.
* Only if you can't find a good solution by using an entry from a controlled vocabularies consider these options:
  1. Look for another controlled vocabulary, or a less closed source, with clear Identifiers. E.g Wikidata or Termdat and use these instead. (Wikidata can always be extend to add new concepts.)
  2. Before not adding an available information, because you can't find a fitting identifier, better add it as text.

### How to store controlled vocabulary Identifiers in Relational Databases. (SQL)
* The preferred approach is to store the complete URI string as a reference to the concept. Often this is done as a STRING field, aside the Primary Key field.
    ```
    CREATE TABLE vocabulary (
        id SERIAL PRIMARY KEY,
        uri TEXT UNIQUE NOT NULL,
        label_en TEXT,
        label_de TEXT,
        label_fr TEXT
    );
    ```
### How to retrieve the labels of an Controlled Vocabualary Entry with an Identifier

Depending how strictly the provider of the controlled vocabulary follows best pratices there are multiple ways to resolve an IRI to the entries labels.

* CVs on the LINDAS platform can be dereferenced:
  With `curl -H "Accept: application/ld+json" -L https://ld.admin.ch/canton/23` the mentioned IRI will answer with, aside other information:
  
  ```
"@id": "https://ld.admin.ch/canton/23",
  "http://schema.org/name": [
    {
      "@language": "de",
      "@value": "Wallis"
    },
    {
      "@language": "fr",
      "@value": "Valais"
    },
    {
      "@language": "it",
      "@value": "Vallese"
    },
    {
      "@language": "en",
      "@value": "Valais"
    }
  ]
  ```

  



* Optional: An explanation how to save an Identifier with its labels in a Relational Database. Especially if we have indirections as in Qualified Attribution etc. 



## Good examples in the wild
* Placeholder to add good examples, once the standard is active.
