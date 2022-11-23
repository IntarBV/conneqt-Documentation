# Navigate-maps

This node creates a button that opens a location in a maps app. This node will be refactored and thus everything on this page is subject to change.

### Node properties

##### Label

The text that shows up on the button.

##### Badge

The script that denotes what text or number shows on the badge of the button.

##### Visible:

Denotes if the button is visible on the screen. This may be changed by other nodes to show or hide the option to click the button with the syntax: `Nodes.BooleanNodeName`

##### Icon

An icon to be displayed left of the text of the button.

##### Color

The color of the badge.

##### FontSize

The size of the text.

##### Location

The location that will be opened on the map. Filled with the following syntax:

    return 'latitude,longitude'

This can also reference other nodes. E.g. we are using a ‘Get geo-location’ node then we use

    return Nodes.Location.coordinates[1] + ',' + Nodes.Location.coordinates[0]

# Example:

--
