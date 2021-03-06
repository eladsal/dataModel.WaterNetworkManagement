# Pipe

## Description
This entity contains a harmonised description of a generic pipe made for the Water Network Management domain. This entity is primarily associated with the water management vertical and related IoT applications. 

	
## Data Model

A JSON Schema corresponding to this data model can be found [here](../schema.json).

### NGSI-LD common Properties
-   `id`: Unique identifier.

-   `type`: Entity type. It must be equal to `PIPE`.

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


### Pipe Entity Properties

-   `initialStatus` : Determines whether the pipe is initially open, closed, or contains a check valve
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text.
    -   Attribute metadata Properties:
        -   Values are resrtricted to: "OPEN","CLOSED","CV"
    -   Mandatory

-   `status` : Dynamic state of the pipe
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text.
    -   Attribute metadata Properties:
        -   Values are resrtricted to: "OPEN","CLOSED"
    -   Mandatory

-   `length` : The actual length of the pipe
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `Metre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTR`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `diameter` : The pipe diameter
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `millimetre`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MMT`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `roughness` : The roughness coefficient of the pipe. It is unitless for Hazen-Williams or Chezy-Manning roughness and has units of millifeet (mm) for Darcy-Weisbach roughness.
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -  Attribute unit: `No unit`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `C62`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `minorLoss` : Unitless minor loss coefficient associated with bends, fittings, etc.
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `No unit`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `C62`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `tag` : An optional text string used to assign the pipe to a category, perhaps one based on age or material
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Optional

-   `description` : A free text description
    -   Optional

-   `bulkCoeff` : The bulk reaction coefficient for the pipe. Use a positive value for growth and a negative value for decay
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `reciprocal day`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `E91`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `wallCoeff` : The wall reaction coefficient for the pipe. Use a positive value for growth and a negative value for decay.
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `mg/m²/day`
    -   Proposed unitCode: `RRC`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional


### Pipe Entity Relationships

-   `startsAt` : The ID of the node where the pipe begins

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

-   `endsAt` : The ID of the node where the pipe ends

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

**Note**: JSON Schemas are intended to capture the data type and associated
constraints of the different Attributes, regardless their final representation
format in NGSI-LD.

### LD Example

A full example is presented [here](../example-normalized-ld.jsonld).

## Use it with a real service

T.B.D.

## Open Issues
