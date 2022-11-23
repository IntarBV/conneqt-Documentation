# Data grid

Displays data in a table by creating a list of grids.

### Node properties

##### Label

The label of the data grid, this text will not be not visible.

##### Selectable

Shows a select box for the user to select a complete row. If this is unchecked, clicking a new row deselects the old row.

##### DefaultSelected

Denotes which row(s) has been selected by default. Use an array to denote the rows: `return[0,1,3]` will have rows 1, 2 and 4 selected by default.

##### Height

Denotes the height of the grid.

##### font Size

Denotes the font size of the text.

##### Data source

The source of the data. The data has to be in an array. All the text can be replaced with a reference to another node with `Nodes.NodeName` as long as the node contains an array.

##### Height

Denotes how tall the rows of the grid are.

##### Row height

Denotes how tall an individual row is. Height/RowHeight will then denote the amount of rows per page.

##### GridDefiniton

Select what data is shown in which cell of the grid. It is possible to make multiple ‘rows’ in a single row in the list. Cells are combined by clicking on one and then dragging across all that need to be combined.

###### Sub-properties:

| name                     | property                                   |
| ------------------------ | ------------------------------------------ |
| Property to show as text | the name of the property show in the cell  |
| interpretate as          | the type of the property shown in the cell |
| Cell color               | The color of the cell background           |
| Text color               | The color of the text                      |
| Text size                | the size of the text                       |
| Text alignment           | the alignment of the text                  |
| Text weight              | when checked, the text is emboldened       |

##### Validate

When checked this control checks if the user has filled in all fields that have the ‘Mandatory’ property checked.

# Examples:

[Report a problem (status update)](../../Nodes/Examples/ReportAProblem.md)
