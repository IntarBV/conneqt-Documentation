# Filter by identifier

Find an asset by its unique identifier. The node can then be used to reference one or multiple of the properties of this asset. The main reason to use this node is to set an asset as a property.

### Node properties

##### AssetID

Select the unique identifier of the asset to find.

### Referencing

This node returns all the information stored in an asset. So there is quite a lot of info to sift through. This can all be referenced using one of the following commands:

    Nodes.Nodename.PropertyName
    Nodes.Nodename.PropertyName[X] /* if the property is a multi-value */
    Nodes.Nodename.BranchName.PropertyName /* if the property is placed inside a branch */
    Nodes.Nodename.BranchName[X].PropertyName /* if the branch is a list */
    Nodes.Nodename.BranchName[X].PropertyName[Y] /* if the branch is a list and the property is a multi-value */

When referencing a multi-value or a branch list, X (or Y) is the position in the list. Keep in mind that this is an array, thus the first position is 0, the second is 1, etc.

# Example:

[Report a problem](../../Nodes/Examples/ReportAProblem.md)
