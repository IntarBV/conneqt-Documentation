# Date and time input

Display a date and time picker field. When the user clicks on this, an agenda and timer folds out.

### Node properties

##### Label

The text displayed above the picker.

##### DefaultValue

The default value until another is picked. Leaving this field empty will cause the node to use the time and date when the node is called as its default.

##### Visible

Denotes if the picker can be seen by the user. This can be influenced by other nodes to show or hide the picker with the syntax: `Nodes.BooleanNodeName`.

##### Mandatory

Denotes if the date and time are mandatory. This will also show a red ‘\*’ next to the header.

### Referencing:

The node will put out a time and date variable. It can be referenced using `Nodes.Nodename`
**Note:** the node will only return something if a trigger is pressed after the node is triggered (e.g. a button).

# Example:

[Place Reservation](../../Nodes/Examples/PlaceReservation.md)
