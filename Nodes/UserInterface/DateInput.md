# Date input

Displays a date picker field. When the user clicks this field, it unfolds an agenda.

### Node properties

##### Label

The text displayed above the picker

##### DefaultValue

The default value until another is picked. Leaving this field empty will cause the node to use the date when the node is called as its default.

##### Visible

Denotes if the picker can be seen by the user. This can be influenced by other nodes to show or hide the picker with the syntax: `Nodes.BooleanNodeName`

##### Mandatory

Denotes if the date is mandatory. This will also show a red ‘\*’ next to the header.

### Referencing:

The node will simply put out a time and date variable with the time set to 22:00 (10 PM). It can be referenced using `Nodes.Nodename`
**Note:** the node will only return something if a trigger is pressed after the node is triggered (e.g. a [button](Https://site/Documentation/Nodes/Button))

# Example:

[Place a reservation](../../Nodes/Examples/PlaceReservation.md) **Note:** this example uses the ‘[Date and time input](../../Nodes/UserInterface/DateAndTimeInput.md)’ node instead of the ‘Date input’ node, but the nodes work virtually the same.
