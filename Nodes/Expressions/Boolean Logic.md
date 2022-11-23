# Boolean Logic

Execute an expression which result is either true or false

### Node properties

##### NodeExpression

The NodeExpression is used to write the formula that determines wheter the boolean will return true or false. The node needs to reference other nodes, otherwise it will always return the same result. To reference the value of a node, use one of the folowing commands:

    Nodes.Nodename.PropertyName
    Nodes.Nodename.PropertyName[X] /* if the property is a multi-value */
    Nodes.Nodename.BranchName.PropertyName /* if the property is placed inside a branch */
    Nodes.Nodename.BranchName[X].PropertyName /* if the branch is a list */
    Nodes.Nodename.BranchName[X].PropertyName[Y] /* if the branch is a list and the property is a multi-value */

Then, make a comparison with one of the folowing statements, where X,Y or both are references to other nodes.

| Statement | True when                                 |
| --------- | ----------------------------------------- |
| X==Y      | X equals Y                                |
| X<Y       | X is smaller than Y                       |
| X>Y       | X is greater than Y                       |
| X<=Y      | X is smaller than or equal to Y           |
| X>=Y      | X is greater than or equal to Y           |
| X!=Y      | X is not equal to Y                       |
| X===Y     | X is equal to and the same data type as Y |

### Returns

This node returns either true or false, depending on the result of the comparison.

# Examples:

[Desserts](../../Nodes/Examples/Desserts.md)

[Create an account](../../Nodes/Examples/CreateAccount.md)
