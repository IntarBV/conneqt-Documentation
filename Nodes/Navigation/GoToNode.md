# Go to Node

Jump to a node somewhere else in the flow. All the results of the nodes down from the targeted node will be cleared. This node can also be created by dragging an output to another node earlier in the flow.

**Note:** The way the ‘Go to node’ node works is that it checks the nodes in reverse order from its position for their identifier. If it is not the correct identifier it removes all that the node has returned and all UI elements will be removed for the next render cycle. This means that if you add non-interupting UI nodes (e.g. ‘Image’ or ‘Clear controls from screen’) right before a ‘Go to node’ node, these nodes will not be loaded into the next render cycle and thus not show up.

### Node properties

##### nodeId

The identifier of the node to jump to.

##### Output:

This node is technically an end node so it cannot have an output.

##### Reference:

This node cannot be referenced.

# Examples:

[Desserts](../../Nodes/Examples/Desserts.md)

[Create account](../../Nodes/Examples/CreateAccount.md)

[Place reservation](../../Nodes/Examples/PlaceReservation.md)

[Report a problem (Status update)](../../Nodes/Examples/ReportAProblem.md)
