# Metadata Guidelines - Ontology and Other Resource

## Resource Summary

| Property Name | Annotation Property | Rationale | Guideline |
| ----------- | -------- | ------- | -------- |
| Title | coreao:title | Understanding | Required |
| Description | coreao:description | Understanding | Required |
| Version | owl:versionInfo | Versioning | Required |
| Namespace Prefix | coreao:preferredPrefix | Identifying | Required |
| Namespace URI | coreao:namespaceURI | Identifying | Required |
| Created By | coreao:createdBy | Provenance and attribution | Recommended |
| Creation Date | coreao:created | Provenance | Recommended |
| Modified By | coreao:modifiedBy | Provenance and attribution | Recommended |
| Modified Date | coreao:modified | Provenance | Recommended |
| Issued Date | coreao:issued | Provenance | Optional |
| Contributor| coreao:contributor | Provenance and attribution | Optional |
| Backward Compatibility | owl:backwardCompatibleWith | Version compatibility | Optional |
| Incompatibility | owl:incompatibleWith | Version compatibility | Optional |

For consistency, it is suggested that required and recommended metadata are
listed in the order shown in the table above.

Some general metadata properties are suitable for additional resource metadata options.

## Guidelines for Required Resource Metadata

### Title

Description:

    A human-readable ontology name

Format:

    First letter of all words capitalized
    Use only spaces as word separators (CamelCase or symbols should not be used as a means of word separation)
    Include language tag
    No ending punctuation

Example:

    coreao:title "Xxxxx Xxxxxxx Xxx"@en

### Description

Description:

    A statement that represents the concept of the ontology

Format:

    First letter of first word capitalized
    Use only spaces as word separators (CamelCase or symbols should not be used as a means of word separation)
    No ending punctuation required
    Complete sentence(s) preferred, but not required
    Include language tag

Example:

    coreao:description "Xxxxxx xxx xxxxxxx xx xxxxxxxxx"@en

### Version

Description:

    Record keeping method to note a new form of the resource
    A modification date should accompany a version update

Format:

    In semantic versioning, each version identifier should follow the format X.Y.Z, where:
    X represents a major version (e.g., defining a set of classes and properties to support new use cases)
    Y represents a minor version (e.g., adding a single property or class)
    Z represents patches or quick bug fixes (updating a label, adding examples, etc.)

Example:

    owl:versionInfo "1.0.0"

### Namespace Prefix

Description:

    Prefix to use when referencing ontology in RDF documents
    Value is the ontology ID = project ID + 'o'

Format:

    Character string of 4-10 length with no spaces
    All lowercase characters
    No ending punctuation
    No language tag

Example:

    coreao:preferredPrefix "xxxx"

### Namespace URI

Description:

    Ontology scope and grouping for classes and properties 

Format:

    Typical URL/URI format
    Character string with no spaces
    All lowercase characters
    No ending punctuation
    No language tag

Example:

    coreao:namespaceURI "https://semantic-data.jlh.com/im/jlh/jlhao#"

### Created and Modified Details

Description:

    Name and other information about the author or modifier of the ontology
    Date when ontology created or changed
    A modification date entry should accompany a version update

Format:

    For createdBy and modifiedBy:
        Author or maintainer full name
        Use only spaces as word separators (CamelCase or symbols should not be used as a means of word separation)
        No ending punctuation
        No language tag
    
    For created and modified:
        Date in YYYYMMDD format
        No ending punctuation
        No language tag

Examples:

    coreao:createdBy "Xxxx Xxxxxx"
    coreao:created "YYYYMMDD"
    coreao:modifiedBy "Xxxxxx Xxxxxx"
    coreao:modified "YYYYMMDD"

    coreao:createdBy [ rdf:type coreo:Person ;
                            coreo:email <mailto:firstName.lastName@cargill.com> ;
                            rdfs:label "FirstName LastName"
                            ] ;

## Other Metadata
