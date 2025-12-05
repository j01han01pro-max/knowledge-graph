# Metadata Guidelines - Class and Property

## Guidelines for Class/Property Metadata

### Local Unique Identifier (LUI)

Description:

    Token appended to the ontology namespace to create the URI

#### Content for Classes and Properties

| Guideline | Example/Clarification |
| --------- | -------- |
| Only alpha-numeric characters - no symbols, special characters or punctuation | Use characters A-Z, a-z, 0-9 |
| Avoid character formation - use plain ASCII format, avoid accents | 'Telephone' or 'Telefono' instead of 'Teléfono' |
| Expand abbreviations and acronyms, unless it is the common term used | Use 'LineOfBusiness' instead of 'LOB'; Use 'SKU' instead of 'Stock Keeping Unit', since it is not well known |
| Avoid the use of homonyms (if unavoidable, use clarifying adjective or adverb or make sure context is clear) | Is 'Bat' a flying animal or baseball bat?; Is 'Saw' a hand-tool or looked at?; Is 'Ship' a big boat or sent something? |

#### Format for Classes and Properties

| Guideline | Example/Clarification |
| --------- | -------- |
| No spaces in or around value | Use 'LegalDocument' not 'Legal Document'; use 'Batch' not ' Batch' |
| Case-sensitive | 'Telephone' or 'Telefono' instead of 'Teléfono' |
| Use all upper case for acronyms | 'ID' instead of 'id' |

#### Class-Specific Content

| Guideline | Example/Clarification |
| --------- | -------- |
| Use singular rather than plural | 'Service' instead of 'Services' |
| Use explicit and concise names | 'WallOfEsophagus' or 'EsophagusWall' instead of 'WallOfTheEsophagus' |

#### Class-Specific Format:

| Guideline | Example/Clarification |
| --------- | -------- |
| First word starts with upper case | 'Document', 'Material' |
| Subsequent words start with upper case with no spaces (use CamelCase notation) | 'BillOfMaterials', 'SalesOrganization' |

#### Property-Specific Content

| Guideline | Example/Clarification |
| --------- | -------- |
| Format for singular subjects and objects | 'connects' instead of 'connect', 'hasColumn' instead of 'hasColumns' |
| Use explicit and concise names | 'payloadVolume' instead of 'dataPayloadVolume' if associated with class Data; 'similarTo' instead of 'isSimilarTo' |

#### Property-Specific Format

| Guideline | Example/Clarification |
| --------- | -------- |
| First word starts with lower case | 'organizes', 'about' |
| Subsequent words start with upper case with no spaces | 'isDefinedBy', 'typeOfData', 'madeFrom' |

### Definition

Content:

    A statement that represents the concept and essential nature of the class
    Only one definition for a class
    Multiple instances can exist with each containing the same definition, but in different languages

Format:

    First word capitalized
    Use only spaces as word separators (CamelCase or symbols should not be used as a means of word separation)
    Use complete sentence(s)
    Include ending punctuation
    Include language tag

Example:

    coreao:definition "Xxxx."@en

Required: Yes
Multiple allowed: Yes

### Note - Other

e.g. changeNote, description, editorialNote, explanatoryNote, scopeNote, usageNote

Content:

    A statement that represents the concept and essential nature of the class
    Only one definition for a class
    Multiple instances can exist with each containing the same definition, but in different languages

Format:

    First word capitalized
    Complete sentence
    Include ending punctuation
    Include language tag

Example:

    coreao:usageNote "Xxxx."@en

Required: No
Multiple allowed: Yes

### Example/Examples

Format:

    Include language tag
    If exampleValues, no ending punctuation
    If example, first word capitalized, complete sentence, and include ending punctuation

Examples:

    coreao:exampleValues "Xxxx"@en
    coreao:example "Xxxx."@en

Required: No
Multiple allowed: Yes

### Source

e.g. adaptedFrom, directSource

Format:

    If URI, do not include < or >
    If string other than URI, first word capitalized and include language tag

Examples:

    coreao:adaptedFrom "https://www.omg.org/spec/Commons/AnnotationVocabulary/"
    coreao:adaptedFrom "ISO 31-0 Quantities and units"@en

Required: No
Multiple allowed: Yes

### Properties

e.g. requiredProperties, associatedProperties

Format:

    Include property value string
    If object is required, include ->object value string

Example:

    coreao:requiredProperties "hasRole->PrimaryPackagingRole"@en

Required: No
Multiple allowed: Yes

### Label - Other

e.g. alternativeLabel, acronym, abbreviation, synonym, preferredLabel

Format:

    No ending punctuation
    Include language tag

Example:

    coreao:alternativeLabel "xxxx"@en

Required: No
Multiple allowed: Yes

### Label

Content:

Format:

    No ending punctuation
    Include language tag

Example:

    rdfs:label "xxxx"@en

Required: Yes
Multiple allowed: No
