# Update

Find an asset by its identifier and update a specific property value.

### Node properties

##### AssetID

The identifier of the asset to update. This can be set using a reference to an asset identifier stored inside another node. See specific node for referencing.

##### PropertyName

The property that will be updated. Note that this is capital-sensitive.

##### NewValue

The value the property will be set to. This can be set using a reference to a value stored inside another node. See specific node for referencing.

### References:

This node returns **all** the information stored in the asset it updated. So there is quite a lot of info to sift through. This can all be referenced using one of the following commands:

    Nodes.Nodename.PropertyName
    Nodes.Nodename.PropertyName[X] /* if the property is a multi-value */
    Nodes.Nodename.BranchName.PropertyName /* if the property is placed inside a branch */
    Nodes.Nodename.BranchName[X].PropertyName /* if the branch is a list */
    Nodes.Nodename.BranchName[X].PropertyName[Y] /* if the branch is a list and the property is a multi-value */

When referencing a multi-value or a branch list, X is the position in the list. Keep in mind that the first position is 0, the second is 1, etc.

# Examples:

[Report a problem](../../Nodes/Examples/ReportAProblem.md)

[Create account (add avatar)](../../Nodes/Examples/CreateAccount.md)
