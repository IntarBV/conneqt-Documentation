# Aggregate

Find assets by provided filters, (optionally) group the found assets, and calculate aggregates per group.

### Properties

##### Asset type

Select the asset type that is filtered on. This will then give the possibility to further filter on the asset type’s property.

##### GroupFields

In this expression it is possible to set the property that the assets will be grouped on: `return['Properties.PropertyToGroupOn.Value']`. If all the assets of the type should fall into one group, use: `return['Properties.Identifier.Value']`

It is also possible to sort on multiple properties. The amount of groups is then denoted by the amount of different values of the first property times the amount of different values of the second property, etc.. To sort on multiple properties, use: `return['Properties.Letter.Value', 'Properties.Number.Value']`

##### Aggregations

Select the property that will be aggregated and how to aggregate it. Count can always be referenced and does not require a specific AggregationFunction.

    return [{
    	AggregationField: 'Properties.PropertyToAggregate.Value',
    	AggregationFunction: 'Sum' / 'Avg' / 'Min / 'Max'
    }]

It is possible to aggregate multiple properties within a group with:

    return [{
    	AggregationField: 'Properties.PropertyToAggregate.Value',
    	AggregationFunction: 'Sum' / 'Avg' / 'Min / 'Max'
          },{
    	AggregationField: 'Properties.SeccondPropertyToAggregate.Value',
    	AggregationFunction: 'Sum' / 'Avg' / 'Min / 'Max'
    }]

##### Order

In this expression the property to order the groups on is set.

    return {
    	Field: 'PropertyToOrderOn',
    	Desc: true / false              /* The results will be descending while true. */
    }

### Standard reference:

`Nodes.Nodename[X].Aggregation[Y].Value`, where X is the array position of the grouping, and Y the array position of the aggregation field. To reference the ammount of properties used in the aggregation: `Nodes.Nodename[X].Count`

### Example:

[Desserts](../../Nodes/Examples/Desserts.md)
