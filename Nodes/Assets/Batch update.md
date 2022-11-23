# Batch update
Find a specific set of assets by applying a list of filters. Then update the given property of all those assets to a given value.

### Properties
###### Asset type
Allows the assettype to be filtered on to be selected. This will then give the possibility to further filter on assets of the type with a specific value for a property.

##### propertyName
Sets the property to be updated using its name. This is upper case sensitive.

###### New value
The new value the propterty will hold. This can reference the value of another node using the Expression button and the correct reference (see individual nodes)

### Referencing:
The Batch Update node will only store the amount of assets it has updated. It does not store any of the assets it has updated.

# Example:
[Desserts](../../Nodes/Examples/Desserts.md)
