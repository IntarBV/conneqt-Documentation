# Navigate

This node allows you to create a button with notifications. These are very usefull for user navigation within the UI produced by the flow.

### Node properties

##### Label

The text on the button.

##### Badge

The script that determines the number on the badge.

##### Visible

Denotes if the button can be seen by the user. This can be influenced by other nodes to show or hide the checkbox with the syntax: `Nodes.BooleanNodeName`.

##### Icon

An icon that appears left of the text.

##### Color

The color of the badge.

##### FontSize

The size of the text.

### Outputs

The node by default has an output that is triggered when the button is clicked.

### Referencing:

The node will return “Click” if it was clicked.

# Example:

[Report a problem (Status update)](../../Nodes/Examples/ReportAProblem.md)
