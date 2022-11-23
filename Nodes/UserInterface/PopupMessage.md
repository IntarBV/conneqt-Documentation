# Popup message

Displays a notification in a popup that can be dismissed by clicking outside it. This node requires a trigger to activate (e.g. a [button](Https://site/Documentation/Nodes/Button)).

### Node properties

##### Caption

The title of the popup.

##### Message

The body of the popup.

### Outputs

By default the ‘Popup message’ node has an ‘ok’ output. The outputs defined in the output section of the menu will return on the popup as buttons. Their buttons will only be visible when there are nodes connected to the output.

### Referencing:

The node returns the name of the button that was pressed as a string. This can be referenced simply with `Nodes.NodeName`

# Example:

[Run other flow](../../Nodes/Examples/RunOtherFlow.md)

[Report a problem](../../Nodes/Examples/ReportAProblem.md)

[Create account (add avatar)](../../Nodes/Examples/CreateAccount.md)
