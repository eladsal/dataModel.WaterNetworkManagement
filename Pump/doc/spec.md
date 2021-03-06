# Pump

## Description
This entity contains a harmonised description of a generic pump made for the Water Network Management domain. This entity is primarily associated with the water management vertical and related IoT applications.

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

### Pump Entity Properties
-   `tag` : An optional text string used to assign the pump to a category, perhaps based on age, size or location
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Optional

-   `description` : A free text description
    -   Optional

-   `initialStatus` : State of the pump (open or closed) at the start of the simulation period
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text.
    -   Attribute metadata Properties:
        -   Values are resrtricted to: "OPEN","CLOSED","CV"
    -   Mandatory

-   `status` : Dynamic state of the pump
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text.
    -   Attribute metadata Properties:
        -   Values are resrtricted to: "OPEN","CLOSED","CV"
    -   Mandatory

-   `head` : Dynamic head gain by the pump

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   {{Optional/Mandatory}}

-   `power` : The power supplied by the pump
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `Kilowatt`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `KWT`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `speed` : The relative speed setting of the pump 
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `No unit`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `MTS`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `efficCurve` : The ID label of the curve that represents the pump's wire-to-water efficiency as a function of flow rate
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `No unit`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `C62`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

-   `energyPrice` : The average or nominal price of energy in monetary units per kw-hr
    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Property`.Text
    -   Attribute unit: `No unit`
    -   [CEFACT](https://www.unece.org/cefact.html) unitCode: `C62`
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Optional

### Pump Entity Relationships

-   `startsAt` : The ID of the node on the suction side of the pump

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

-   `endsAt` : The ID of the node on the discharge side of the pump

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

-   `pumpCurve` : The ID label of the pump curve used to describe the relationship between the head delivered by the pump and the flow through the pump

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

-   `pumpPattern` : The ID label of a time pattern used to control the pump's operation. The multipliers of the pattern are equivalent to speed settings. A multiplier of zero implies that the pump will be shut off during the corresponding time period

    -   Normative References: {{Add a normative reference}}
    -   Attribute type: `Relationship`.
        {{Add here the description of the target relationship object}}
    -   Attribute metadata Properties:
        -   `{{metadata Property name}}` : {{Metadata Property Description}}
    -   Mandatory

-   `energyPattern` : The ID label of the time pattern used to describe the variation in energy price throughout the day

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
