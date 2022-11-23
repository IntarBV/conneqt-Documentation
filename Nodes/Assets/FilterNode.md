# Filter

Find all assets by applying a list of filters. The output is a list of assets that match all the given filters

### Node properties

##### Asset type:

Select the asset type to filter on, after that the assets can be filtered on property values.

##### Order:

Describe in what order the filtered assets should be returned, where Desc means descending. (order by highest first)

    return {
    	Field: 'PropertyToOrderOn',
    	Desc: true / false  /* when true the values wil sort in a decending order */
    }

##### NodeExpression

In the NodeExpression, the properties that are returned can also be set. It is recommended to always keep the ‘Identifier’ and ‘Name’ part of the return. To add another property to return, use: ReturnName: `x.Properties.PropertyName.Value`, in:

    new Array(conneqt.Assets.Filter($scope.Filters, $scope.Order).Records).map(
        function(x){return {Identifier: x.Identifier, Name: x.Name, >>>here<<< }})

### Referencing:

The filter node returns an array, thus referencing is done using: `Nodes.Nodename[X].ReturnName` Where X is the position within the array.

# Examples:

[Desserts](../../Nodes/Examples/Desserts.md)

[Report a problem (status update)](../../Nodes/Examples/ReportAProblem.md)
