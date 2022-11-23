# Dropdown select list

Creates a dropdown list for the user to pick an option.

### Node properties

##### Label

The text displayed above the list.

##### Visible

Denotes if the list can be seen by the user. This can be influenced by other nodes to show or hide the picker with the syntax: `Nodes.BooleanNodeName`.

##### Mandatory

Denotes if a choice is mandatory.

##### DefaultValue

The default value until another is picked. As of writing this, this is a required field for the node to work.

##### DataSource

The data source used to populate the list. This needs to be an array. A node can be referenced with `Nodes.NodeName` as long as the node contains an array.

##### Columns

**+** creates a new column. The list needs at least one column to work.

| BoundProperty | the property the list will be based off of.                              |
| ------------- | ------------------------------------------------------------------------ |
| Width         | the width of the column.                                                 |
| Color         | the color of the background of the cells.                                |
| TextAling     | the alignment of the text, when nothing is selected, left aling is used. |

### Outputs:

As of writing this, the node has an ‘any result’ and a ‘click’ output. It is not recommended to use these. Rather, use the green output with a button afterwards.

### Referencing:

The node will return everything stored in the selected property. If an asset was stored, it returns all properties that had been set in the Node that acted as the DataSource.

# Examples:

[Report a problem (status update)](../../Nodes/Examples/ReportAProblem.md)
