# Result navigation

Navigate to an entity at flow end.

### Node properties

##### Action

**Do not change.**

##### entityType

The type of entity to navigate to (asset / dashboard / flow).

##### Identifier

The identifier of the entity to navigate to. For flows this can be found under the flow properties menu, assets and dashboards currently do not have a place to find their Identifier, but this can still be done using referencing.

### Outputs

End nodes cannot have any outputs.

### Referencing:

It is not recommended to reference the node. However, the node outputs the following values:

| Key              | Always “Navigate”                          |
| ---------------- | ------------------------------------------ |
| Value.Identifier | The Identifier of the entity navigated to. |
| Value.EntityType | The type of the entity navigated to.       |

# Example:

[Create account (add avatar)](../../Nodes/Examples/CreateAccount.md)
