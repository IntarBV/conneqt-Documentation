# Create (Incl. properties)

Create a new asset of a given type, where specific property values can be predefined. After insertion it will be assigned a unique identifier.

### Node Properties

##### AssetType

Select the type of which the new asset will be created

##### Properties

Set the properties of the asset using the following syntax: `NameOfProperty: 'SetToValue'`
Multiple properties of the same asset can be set by using a comma and adding the property to a new line:

    return{
        NameOfProperty1: 'SetToValue1' ,
        NameOfProperty2: 'SetToValue2'
    }

It is also possible to set properties to values of other nodes by referencing other nodes.

# Examples:

[Desserts](../../Nodes/Examples/Desserts.md)

[Create account](../../Nodes/Examples/CreateAccount.md)

[Report a problem](../../Nodes/Examples/ReportAProblem.md)

[Place reservation](../../Nodes/Examples/PlaceReservation.md)
