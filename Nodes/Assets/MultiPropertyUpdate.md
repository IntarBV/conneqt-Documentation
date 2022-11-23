# Multi-property update

Find an asset by ID and update multiple of its property values.

### Node properties

##### AssetID

The unique ID of the asset that will be updated. An easy way of finding this is by referencing a 'filter' node.

##### Properties

Set the properties of the asset using the following syntax:

    return{
        NameOfProperty: 'SetToValue'
    }

Multiple properties of the same asset can be set by using a comma and adding the property to a new line:

    return{
        NameOfProperty1: 'SetToValue1' ,
        NameOfProperty2: 'SetToValue2'
    }

### Reference:

This node returns **all** the information stored in an asset, not just the updated properties. So there is quite a lot of info to sift through. This can all be referenced using one of the following commands:

    Nodes.Nodename.PropertyName
    Nodes.Nodename.PropertyName[X] /* if the property is a multi-value */
    Nodes.Nodename.BranchName.PropertyName /* if the property is placed inside a branch */
    Nodes.Nodename.BranchName[X].PropertyName /* if the branch is a list */

When referencing a multi-value or a branch list, X is the position in the list. Keep in mind that the first position is 0, the second is 1, etc.

# Example:

[Report a problem (Status update)](../../Nodes/Examples/ReportAProblem.md)
