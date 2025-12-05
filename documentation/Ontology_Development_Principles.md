# Ontology Development

## Ontology

## Classes and Properties

### Declarations

#### Class Type/Property Type

Examples:

    :Association rdf:type owl:Class
    :organizedBy rdf:type owl:ObjectProperty


    Required: Yes
    Multiple allowed: No
    
#### subClassOf/subPropertyOf

Examples:

    rdfs:subClassOf :Organization
    rdfs:subPropertyOf :isDescribedBy


    Required: No
    Multiple allowed: Yes

#### Class/Property Details

e.g. owl:equivalentClass, owl:inverseOf, etc.

Examples:

    owl:equivalentClass
    owl:inverseOf :brandOf


    Required: No
    Multiple allowed: Yes
    
### Domain/Range

Examples:

    rdfs:domain :BillOfMaterials
    rdfs:range :BillOfMaterialsID


    Required: No
    Multiple allowed: Yes **see Notes
  
#### Multiple Domains

When multiple domains are declared for a single property, the interpretation is
that the subject of that property must belong to the intersection of all
declared domain classes. This means if a property hasPart has domains Car and
Vehicle, then anything that hasPart something must be both a Car and a Vehicle.

#### Multiple Ranges

Similarly, when multiple ranges are declared for a single property, the
interpretation is that the object of that property must belong to the
intersection of all declared range classes. If a property isMadeOf has ranges
Metal and Material, then anything that isMadeOf something must be both a Metal
and a Material.

#### Important Considerations

##### Inference

Domain and range statements are not constraints but rather enable a reasoner to
infer further knowledge. If you state that a property's domain is Person, and
you assert that Felix hasAge 9, a reasoner will infer that Felix is a Person.

##### Union of Classes

If you intend for a property's domain or range to be any of several classes
(e.g., a property applies to either a Mountain or a Lake), you should use the
owl:unionOf construct to explicitly define the domain or range as a union of
classes, rather than declaring multiple separate domains/ranges which would
imply an intersection.

##### Subproperties

A common and often more robust approach to handle varying domains and ranges for
similar relationships is to create a hierarchy of properties using
subproperties. A subproperty inherits the domains and ranges of its
superproperty, and you can then declare additional, more specific domains and
ranges for the subproperty as needed.
