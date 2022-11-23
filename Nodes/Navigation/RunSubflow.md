# RunSubflow

Execute another flow inside the current flow. Unlike the dynamic subflow, this flow does not use inputs. It merely triggers the flow and waits for an output.

### Node properties

##### FlowId

The identifier of the flow to execute.

##### Outputs

This node outputs the output of the executed flow. An output can be created by adding a ‘Result action’ node set to output to the executed flow. Multiple outputs can be generated this way.

# Example:

[Run other flow](../../Nodes/Examples/RunOtherFlow.md)
