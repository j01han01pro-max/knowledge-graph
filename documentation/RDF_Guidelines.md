# RDF Guidelines

## RDF Formats

The MDS File Management web application is configured to load N-Quads files to Neptune. 

An N-Triples statement (e.g. record or row) consists of a sequence of three terms representing subject, predicate and object.

        <subject URI> <predicate URI> <object URI or literal> .

An N-Quads statement adds an additional graph term to the end of the sequence, representing subject, predicate, object and graph.

        <subject URI> <predicate URI> <object URI or literal> <graph URI> .

### N-Quads Statement Types

There are 4 general types of statements in RDF N-Quads:

- Class Type
    
    purpose: create a new instance of a class

    format:

        <subject URI> <http://www.w3.org/1999/02/22-rdf-syntax-ns#type> <class URI> <graph URI> .

    examples:

        <https://semantic-data.jlh.com/core/ito/table/customer> <http://www.w3.org/1999/02/22-rdf-syntax-ns#type> <https://semantic-data.jlh.com/im/it/ito#Table> <https:semantic-data.jlh.com/kg/it/itg> .
        <https://semantic-data.jlh.com/core/ito/column/customerid> <http://www.w3.org/1999/02/22-rdf-syntax-ns#type> <https://semantic-data.jlh.com/im/it/ito#Column> <https://semantic-data.jlh.com/kg/it/itg> .

- Metadata
    
    purpose: assign metadata to an instance of a class

    format:

        <subject URI> <annotation URI> <literal> <graph URI> .

    examples:

        <https://semantic-data.jlh.com/core/ito/table/customer> <https://semantic-data.jlh.com/im/jlh/jlhao#prefLabel> "Customer"@en-us <https://semantic-data.jlh.com/kg/it/itg> .
        <https://semantic-data.jlh.com/core/ito/column/customerid> <https://semantic-data.jlh.com/im/jlh/jlhao#prefLabel> "customer_ID"@en-us <https://semantic-data.jlh.com/kg/it/itg> .

- Object Property

    purpose: assign a relationship between two class instances

    format:
    
        <subject URI> <property URI> <object URI> <graph URI> .
    
    examples:

        <https://semantic-data.jlh.com/core/ito/table/customer> <https://semantic-data.jlh.com/im/it/ito#hasColumn> <https://semantic-data.jlh.com/core/ito/column/customerid> <https://semantic-data.jlh.com/kg/it/itg> .
        <https://semantic-data.jlh.com/core/ito/column/customerid> <https://semantic-data.jlh.com/im/it/ito#inTable> <https://semantic-data.jlh.com/core/ito/table/customer> <https://semantic-data.jlh.com/kg/it/itg> .

- Data Property

    purpose: assign a property with a literal value to an instance of a class

    format:
    
        <subject URI> <property URI> <literal> <graph URI> .

    example:

        <https://semantic-data.jlh.com/core/ito/column> <https://semantic-data.jlh.com/im/it/ito#typeOfData> "Decimal"@en-us <https://semantic-data.jlh.com/kg/it/itg> .

### URI Format

A URI is a **unique** and **permanent** identifier for something, and has a format that looks similar to a URL. 

Notice that the URI representing the subject, 'https://semantic-data.jlh.com/core/ito/table/customer', does not change in the examples above. Once a URI is assigned, it is a permanent identifier for that data.

URIs consist of a locator part and an identifier part. The locator part is a static value and indicates the type of item it represents and the identifier part is the unique identifier of the item within the locator realm.

Internal URIs are assigned to a variety of items, all with distinguishing locator values and identifier formats.

#### Information Model (im)

Ontologies
    
    locator: https://semantic-data.jlh.com/im/
    identifier: <project_id>/<ontology_id>
    example: https://semantic-data.jlh.com/im/jlh/jlho

Classes

    locator: https://semantic-data.jlh.com/im/
    identifier: <project_id>/<ontology_id>#<class_label>
    example: https://semantic-data.jlh.com/im/jlh/jlho#UnitOfMeasure

Properties

    locator: https://semantic-data.jlh.com/im/
    identifier: <project_id>/<ontology_id>#<property_label>
    example: https://semantic-data.jlh.com/im/jlh/jlho#includedIn

Annotations

    locator: https://semantic-data.jlh.com/im/
    identifier: <project_id>/<ontology_id>#<annotation_label>
    example: https://semantic-data.jlh.com/im/jlh/jlhao#altLabel

Currently, the only annotations allowed are in the Core Annotation Ontology with URI format 'https://semantic-data.jlh.com/im/jlh/jlhao#<annotation_label>'.

#### Knowledge Graph (kg)

Graphs

    locator: https://semantic-data.jlh.com/kg/
    identifier: <project_id>/<graph_id>
    example: https://semantic-data.jlh.com/kg/core/coreg

#### Data (core)

Data Instances

    locator: https://semantic-data.jlh.com/core/
    identifier: <ontology_id>/<class_name>/<data_label>
    example: https://semantic-data.jlh.com/jlh/jlho/unitofmeasure/kilogram

### N-Quads Format

The whitespace following subject, predicate, and object MUST be a single space, (U+0020).
The sequence MUST be terminated by a '.' and a new line.
There MUST be no comments.
HEX MUST use only uppercase letters ([A-F]).
Characters MUST NOT be represented by UCHAR.
Within STRING_LITERAL_QUOTE, only the characters U+0022, U+005C, U+000A, U+000D are encoded using ECHAR. ECHAR MUST NOT be used for characters that are allowed directly in STRING_LITERAL_QUOTE.
An N-Quads document is encoded in UTF-8.

Resource: https://www.w3.org/TR/n-triples/

Internally - no blank nodes

The RDF N-Quads file is searched and parsed to determine the type of data, based on the criteria section and description and in the order below.

Data              | Criteria  | Criteria                                                         | Criteria  | Criteria                                                         |
Type              | Term 1    | Description 1                                                    | Term 2    | Description 2                                                    |
----------------- | --------- | ---------------------------------------------------------------- | --------- | ---------------------------------------------------------------- |
prefLabel         | 2nd       | equals 'https://semantic-data.jlh.com/im/jlh/jlhao#prefLabel'  |           |                                                                  |
altLabel          | 2nd       | equals 'https://semantic-data.jlh.com/im/jlh/jlhao#altLabel'   |           |                                                                  |
class type        | 2nd       | equals 'http://www.w3.org/1999/02/22-rdf-syntax-ns#type'         |           |                                                                  |
metadata          | 2nd       | contains 'https://semantic-data.jlh.com/im/jlh/jlhao#'         | 2nd       | text after '#' is NOT 'prefLabel' or 'altLabel'                  |
data property     | 3rd       | does not contain 'https://semantic-data.jlh.com/core/'           |           |                                                                  |
object property   | 3rd       | contains 'https://semantic-data.jlh.com/core/'                   |           |                                                                  |

## Canonical Catalog Process

## What is 'Canonical'?

A canonical URI is the single, authoritative identifier chosen to represent a thing
(class, property, or individual) in the graph — even if that thing has multiple
possible names, spellings, or identifiers elsewhere.

It’s the “one URI to rule them all” for that entity in the dataset.

### Why It Matters

In the real world, the same concept can be described in different ways:
- centimeter vs. centimetre
- United States vs. USA vs. U.S.A.

If every spelling or source is used to mint a new URI, the graph will end up with
duplicates and fragmentation.

A canonical URI solves that by saying:

👉 “In the graph, :centimeter is the official URI. Any other variant points back to this one.”

### Benefits

- Prevents duplicates caused by spelling/synonyms.
- Keeps the graph clean (one URI per entity).
- Lets users store alternative labels and external references for interoperability.
- Works in Neptune without needing a reasoner.

## RDF Data Processing

### File Processing

Data is processed in the following order, once uploaded in the web application:

1. XLSX Data File Conversion to CSV *(uploaded .xlsx files)*
2. CSV Data Cleansing *(uploaded .csv and .xlsx files)*
3. Mapping File Retrieval from S3 *(uploaded .csv and .xlsx files)*
4. CSV Data File Conversion to RDF N-Triples *(uploaded .csv and .xlsx files)*
5. RDF N-Triples Conversion to RDF N-Quads *(all files)*
6. Canonical Processing *(all files)*

During canonical processing, certain assumptions are made about the RDF
N-Quads data, as described in the next section.

    > If the RDF file is formatted using a mapping file, the SPARQL code must
    follow the guidelines in the example mapping template provided by the MDS Team.
    
    > If the RDF file is formatted manually for upload, the author is
    responsible for the data complying with the guidelines.

### N-Quads Format

The RDF N-Quads file is searched and parsed to determine the type of data, based on the criteria section and description and in the order below.

Data              | Criteria  | Criteria                                                         | Criteria  | Criteria                                                         |
Type              | Section 1 | Description 1                                                    | Section 2 | Description 2                                                    |
----------------- | --------- | ---------------------------------------------------------------- | --------- | ---------------------------------------------------------------- |
prefLabel         | 2nd       | equals 'https://semantic-data.jlh.com/im/jlh/jlhao#prefLabel'  |
altLabel          | 2nd       | equals 'https://semantic-data.jlh.com/im/jlh/jlhao#altLabel'   |
type (class)      | 2nd       | equals 'http://www.w3.org/1999/02/22-rdf-syntax-ns#type'         |
metadata          | 2nd       | contains 'https://semantic-data.jlh.com/im/jlh/jlhao#'         | 2nd       | text after '#' is NOT 'prefLabel' or 'altLabel' |
data property     | 3rd       | does not contain 'https://semantic-data.jlh.com/core/'           | 
object property   | 3rd       | contains 'https://semantic-data.jlh.com/core/'                   |

The canonical processing assumes the following are true:

coreao:prefLabel used to assign the 'official' label for the instance

all labels will have a language tag
if label has no language tag - lang tag will default to en-us
all pref labels will be in en-us
each pref label statement will have 1 corresponding type statement
alt labels, metadata and property statements reference an existing instance or one created in the same data file

metadata statements - add as altLabel if IN ('abbreviation', 'acronym', 'symbol', 'synonym')

### Canonical Formation Guidelines

All data URIs must start with the static string 'https://semantic-data.jlh.com/core/'.

All characters after the static string form the canonical value and should include:
<ontology_id>/<class_name>/<instance_label>

**ontology id**: the (lowercase) 4-8 char length id of the ontology where the class is defined;
value is also the preferred prefix of the ontology

**class name**: lowercase name of class, as defined in the ontology and the type declaration

**instance label**: the string value in prefLabel statements with the following modifications:

lowercase
remove language tag
replace "[ñ]" with "n", "[áàâäã]" with "a", "[éèêë]" with "e", "[íìîï]" with "i"
replace anything not in a-z, 0-9 and spaces with ""
trim leading and trailing whitespace
replace spaces with "-"
reduce multiple instances of "-" to single instance
