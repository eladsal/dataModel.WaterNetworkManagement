# Tank

## Description
This entity contains a harmonised description of a generic Tank made for the Water Network Management domain. This entity is primarily associated with the water management vertical and related IoT applications.

## Data Model

A JSON Schema corresponding to this data model can be found [here](../schema.json)

### NGSI-LD common Properties
-   `id`: Unique identifier.

-   `type`: Entity type. It must be equal to `Junction`.

-   `modifiedAt`: Last update timestamp of this
    entity.

    -   Attribute type: Property. [DateTime](https://schema.org/DateTime)
    -   Read-Only. Automatically generated.

-   `createdAt`: Entity's creation timestamp.

    -   Attribute type: Property. [DateTime](https://schema.org/DateTime)
    -   Read-Only. Automatically generated.

-   `location` : Location of Junction represented by a GeoJSON geometry.

    -   Attribute type: `GeoProperty`
    -   Normative References:
        [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    -   Mandatory.


### Tank Enity Properties

-   `tag` : An optional text string used to assign the tank to a category, such as a pressure zone
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Optional

-   `description` : A free text description
    -   Optional
-   `demandCategory` : {{Description of the Attribute}}
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   `baseDemand`: A sub-property.
    -   `demandPattern`: A sub-Relationship
    -   Optional

-   `elevation` : The elevation above some common reference of the tank
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `Metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTR`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `sourceCategory` : Description of the quality of source flow entering the network at a specific node

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   `sourceType`: A sub-property.
    -   `sourceQuality`:A sub-property.
    -   `sourcePattern`: A sub-Relationship.

-   `sourceType` : A sub-property of the Property `sourceCategory`
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -  Values Restricted to : "CONCEN", "MASS", "FLOWPACED" and "SETPOINT"
    -   Mandatory

-   `sourceQuality` : Baseline or average concentration (or mass flow rate) of source. A sub-property of the Property `sourceCategory`
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    Attribute unit: `Mg/L`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `M1`
    -   Mandatory

-   `initLevel` : The height of the water surface above the bottom elevation of the tank at the start of the simulation
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `Metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTR`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `minLevel` : The height of the water surface above the bottom elevation of the tank at the start of the simulation
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `Metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTR`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `maxLevel` : The height of the water surface above the bottom elevation of the tank at the start of the simulation
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `Metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTR`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `minVolume` : The volume of water in the tank when it is at its minimum level
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `cubic metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTQ`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `nominalDiameter` : The diameter of the tank
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `Metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTR`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `mixingModel` : A sub-property of the Property `sourceCategory`
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -  Values Restricted to :  "MIXED", "2COMP", "FIFO" and "LIFO"
    -   Mandatory

-   `volumCurve` : The ID label of a curve used to describe the relation between tank volume and water level
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `cubic metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTQ`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `mixingFraction` : The fraction of the tank's total volume that comprises the inlet-outlet compartment of the two-compartment (2COMP) mixing model
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `No unit`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `C62`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

### Tank Enity Relationships

-   `demandPattern`: A relationship to the pattern pf the `demandCategory` property
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

-   `sourcePattern` : A relationship to the pattern pf the `sourceCategory` property
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

**Note**: JSON Schemas are intended to capture the data type and associated
constraints of the different Attributes, regardless their final representation
format in NGSI(v2, LD).

### LD Example

A full example is presented [here](../example-normalized-ld.jsonld).

## Use it with a real service

T.B.D.

## Open Issues

