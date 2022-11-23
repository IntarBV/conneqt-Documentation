# Result Action

Execute an action when the flow is finished.

### Node properties

| Action         |                                                                                                          |
| -------------- | -------------------------------------------------------------------------------------------------------- |
| Output         | The node will output all the data stored in it. Can be used with ‘Run dynamic subflow’ to return values. |
| Close          | The Flow will simply end.                                                                                |
| Navigate       | Recommended to use the ‘Result navigation’ node.                                                         |
| Run other flow | Recommended to use the ‘Follow up Flow’ node.                                                            |

### Outputs

A flow end node cannot have any outputs

### Referencing

It is not recommended to reference the output node, but it is possible.

# Example:

Output: [Run other flow](../../Nodes/Examples/RunOtherFlow.md)
