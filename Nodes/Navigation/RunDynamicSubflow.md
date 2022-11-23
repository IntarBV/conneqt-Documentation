# Run dynamic subflow

Execute a runtime decided flow inside the current flow. Unlike the Run subflow node, it can overwrite which flow to run.

### Node properties

##### FlowId

The identifier of the standard flow to be executed

##### DynamicFlowId

The target flows to run. This overwrites the flowId. Syntax: `Nodes.NodeName`, the node NodeName should be an [Expression](../../Nodes/Expressions/Expression.md) or similar node that contains the identifier for the flow to be executed.

##### Flow.inputs.values

Add input values to be used in the subflow.

##### Outputs

Outputs the output of the executed flow.

# Example:

[Run other flow](../../Nodes/Examples/RunOtherFlow.md)
