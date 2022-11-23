# Flows

![Button](Documentation/Flow/0.png)

The flows are the ‘code’ of conneqt. With flows, data within a conneqt tennant can be created and managed. A flow is created by combining blocks, known as nodes, in order. When creating a new flow, a starting node is created. The header of the flow can be changed by changing the ‘Unnamed process’ within the NodeExpression of this node. Nodes are added by clicking the output dots on existing nodes (or dragged to them from the toolbox). This will also create a line or ‘path’ between these nodes. With these paths, the actions of the flow can be visualised. When using multiple outputs from one node, a decision tree is created that can yield different results based on the steps of the flow.

When clicking on a node, an edit screen opens up on the right. The first option will always be a name for the node. A good convention here is to use lowercase names. This will make more sense if the flow becomes complex enough that small bits of Javascript are used.

After that, Node specific options will follow. See the node specific pages listed below for these. Every node also has a NodeExpression. This field denotes what the node does, and may be altered to manipulate the behaviour or outputs of the node.

### Outputs

Towards the bottom of the edit screen, there is the Outputs tab. For some nodes outputs have already been created as they are expected to happen when executing the node. But all nodes can have up to 3 different kinds of output added to the list, and there is always the option to continue regardless of the result.

![Node](Documentation/Flow/1.png)

The ‘Specific result’ output will show up as a blue dot attached to the node with the specified value above it. This output will trigger in case the specified result matches the result of the node. Multiple of this output can be added. The ‘Any result’ output will also show up as a blue dot attached to the node, but this time without a value above it. This output will trigger in case the result is not empty (null) and not a value denoted in a ‘Specific result’ output. Only one of this output can be added. The ‘Any error’ output will show up as a red dot attached to the node. This output will trigger in case the node returns an error. Only one of this output can be added. Whenever a node returns ‘null’ (noting), the flow stops at that node.

The green dot attached to the node does not have an assigned output, it will always trigger, regardless of the result. Even if the node returns null. It is not possible to have a node connected to the green dot and another output type, but it is possible to pass an output through the next node by attaching the node to pass it through to the green dot.

![Seperated](Documentation/Flow/2.png) ![Connected](Documentation/Flow/3.png)

Finally, there is the Scheduled execution. Once this is enabled the node will only send the execution to the server without waiting for a reply. This is useful for optimisation. In the description, a tag can be added under TagName. This tag will show up on devices that have yet to sync all their data as a description of what still has to be synced

The remarks field can be used to leave notes on the nodes. A text bubble will show up on the node signifying that a remark was added.
![Comment](Documentation/Flow/4.png)

### Types of nodes

There are two main types of nodes: Expression Nodes and User-Interaction nodes

The yellow Expression nodes are nodes in control of calculations and data manipulation. These handle all the behind the scenes and are all executed on the server. The expression could be a very simple comparison, but also a highly complex function. The result will stay available for the continued duration of the execution of the flow. Most can be referenced with the syntax:`Nodes.NodeName`, where NodeName is the name of the node calculating the value to reference. This line is added in the node propery expression after clicking the expression button![nodeExpression](Documentation/flow/41.png). At times, nodes may have multiple outputs in what is called an array. If a specific output has to be referenced, it is done with:`Nodes.NodeName[X]`, where the X is the position of the desired value. Keep in mind that this is an array position, thus the X for the first position is 0, for the second it’s 1, for the third it’s 2, etc.

Once a flow is run, a small bit of the return will appear on the right side of nodes.

![Return](Documentation/Flow/5.png)

Clicking on these will show a screen with all the information stored inside the node. Every step to the right is a branch, and all these trees are different for each node. Value stored in deeper levels of these branches has to be accessed specifically. (see the [desserts](Nodes/Examples/Desserts.md) example on the 'Aggregate' node for more information.)

The blue User Interface nodes are nodes that interact with the user, either by displaying something (an image, text, output value, etc.) or asking for an input. These nodes are especially useful when the flow has the user create an asset. These UI elements can be rendered in different kinds of clients. E.g. the angular portal, the conneqt xamarin app or (to an extent) in the telegram chat app. User interface nodes are first sent to the client before being rendered. No UI element is rendered on the conneqt server. UI nodes are stacked and rendered at the same time when connected using the green dots. If the nodes are connected using other outputs, they wait for the certain output to be triggered. Using the 'Clear screen' Node removes all the UI elements on the screen. It is important to know that all these nodes are ‘stacked’ and executed all at once in a render cycle, these happen when the flow waits for user input. Thus if there are multiple nodes that show something, and then immediately after that a 'Clear screen' node is used, none of the nodes will actually present something. Similarly, if a ‘Go to node’ node is used right after UI nodes that do not require user input -thus not triggering a render cycle- the UI elements won’t show up.

The red End nodes are nodes that trigger something outside the program, and cannot have an output. The purple Sub flow nodes start another flow and may have the result of that flow as its output. The green ‘Go to node’ node can be used to create loops and also cannot have an output.

## Triggers

Flows can be called using triggers. These can be denoted in an Assettype, asset or another flow. Then they can be activated in 4 different ways

- On the creation of an asset
- On the changing of a property of an asset
- From another flow.
- Form a user interface (dashboards, asset lists, etc.)

While the first three happen in the background, the final activation method relies on a user pressing a button. A trigger is created by adding a flow as a trigger to a property of an asset(type) or using one of the subflow nodes in another flow.

## Flow queue

When activating a trigger for all assets inside a filter with many assets or triggering multiple subflows at once, they cannot all be processed at the same time. Thus, they are moved to the queue. The process queue gives an overview of which processes have been planned, when they had been planned, their input data, when they started their execution and when they finished processing.

## Flow results

When flows have been triggered, they are also stored inside the flow results. This will show the date and time the flow was run, the name of the flow, which asset it was assigned to, the current status of the flow, the version and whether the flow was a concept or had already been published.

| Interface                            |                                                                                                                                                                                                                                                           |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![Button](Documentation/Flow/6.png)  | The publish button publishes the flow. This means that the flow can be referenced and used by the rest of the tenant.                                                                                                                                     |
| ![Button](Documentation/Flow/7.png)  | The discard concept button returns the flow to the last published version.                                                                                                                                                                                |
| ![Button](Documentation/Flow/8.png)  | The load test data button allows for revision of older tests by loading them. This will fill in the returns of the nodes used in the flow, but does not run the flow again. This is only possible when the flow is left unchanged after running the test. |
| ![Button](Documentation/Flow/9.png)  | The start test with asset button allows for manual selection of an asset to test the flow with                                                                                                                                                            |
| ![Button](Documentation/Flow/10.png) | The start test button starts running the flow without any given data.                                                                                                                                                                                     |
| ![Button](Documentation/Flow/11.png) | The remove button deletes the currently opened flow. This action cannot be undone.                                                                                                                                                                        |
| ![Button](Documentation/Flow/12.png) | The add to dashboard is a quick way to add a trigger button to a dashboard.                                                                                                                                                                               |
| ![Button](Documentation/Flow/13.png) | The properties button accesses the flow’s properties.                                                                                                                                                                                                     |
| ![Button](Documentation/Flow/14.png) | The toolbox contains all nodes that can be dragged and dropped into a flow.                                                                                                                                                                               |
| ![Button](Documentation/Flow/15.png) | The auto layout button reorganises the flow in an orderly manner.                                                                                                                                                                                         |
| ![Button](Documentation/Flow/16.png) | The undo and redo buttons undo and redo any action performed in the editor.                                                                                                                                                                               |
| ![Button](Documentation/Flow/17.png) | The generate token button allows for the flow to be triggered from a webapp. The link to this app will be : `https://api-test.conneqt.com/flow/pwa/?otp=` with the generated token added to the end.                                                      |
| ![Button](Documentation/Flow/18.png) | The generate subflow button turns all selected nodes into a subflow.                                                                                                                                                                                      |
| ![Button](Documentation/Flow/19.png) | The group nodes button adds nodes to a Node form, a collapsable collection of nodes.                                                                                                                                                                      |
| ![Button](Documentation/Flow/20.png) | This means that the current flow has not been published and thus cannot be referenced anywhere.                                                                                                                                                           |
| ![Button](Documentation/Flow/21.png) | This means that the current flow has been published and can be referenced and triggered anywhere in the tennant.                                                                                                                                          |

| Flow properties settings |                                                                                                                                                                                                                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Name                     | The name of the flow                                                                                                                                                                                                                                                           |
| Icon                     | The icon of the flow                                                                                                                                                                                                                                                           |
| App name                 | A website that triggers a flow can be downloaded as an app on certain devices (android and windows, both via google chrome, have successfully been tested). This option sets the name of this app. If left empty the app will use the name of the flow as the name of the app. |
| Command (Telegram)       | The command that will trigger the flow when using the telegram bot.                                                                                                                                                                                                            |
| Input parameters         | These can be set by certain triggers to have the flow start with certain parameters that can be accessed by its nodes.                                                                                                                                                         |
| FlowInfo                 | Information on the flow.                                                                                                                                                                                                                                                       |
| Node Names               | A list of all the named nodes and their properties                                                                                                                                                                                                                             |

| List of all nodes:                                                             | Symbol                                           | Description                                                                                     |
| ------------------------------------------------------------------------------ | ------------------------------------------------ | ----------------------------------------------------------------------------------------------- |
| **Assets**                                                                     |                                                  |                                                                                                 |
| [Aggregate](Nodes/Assets/Aggregate.md)                                         | ![Symbol](Documentation/Flow/NodeSymbols/0.png)  | Preform calculations on data.                                                                   |
| [Batch update](Nodes/Assets/Batch%20update.md)                                 | ![Symbol](Documentation/Flow/NodeSymbols/1.png)  | Update a property of multiple assets of the same asset type at once.                            |
| [Create (incl. Property values)](Nodes/Assets/CreateByPayload.md)              | ![Symbol](Documentation/Flow/NodeSymbols/2.png)  | Create a new asset of an assettype and set its properties.                                      |
| [Filter](Nodes/Assets/FilterNode.md)                                           | ![Symbol](Documentation/Flow/NodeSymbols/3.png)  | Generate a list of assets based on filter parameters.                                           |
| [Find by identifier](Nodes/Assets/FilterID.md)                                 | ![Symbol](Documentation/Flow/NodeSymbols/4.png)  | Find an asset by its unique identifier.                                                         |
| [Multi-property update](Nodes/Assets/MultiPropertyUpdate.md)                   | ![Symbol](Documentation/Flow/NodeSymbols/6.png)  | Update multiple properties of the same asset at once.                                           |
| [Update](Nodes/Assets/Update.md)                                               | ![Symbol](Documentation/Flow/NodeSymbols/7.png)  | Update a property of an asset.                                                                  |
| **Communication**                                                              |                                                  |                                                                                                 |
| [Message person using medium](Nodes/Communication/MessagePersonUsingMedium.md) | ![Symbol](Documentation/Flow/NodeSymbols/11.png) | Send a message to someone who is part of the tennant using SMS, email or the Telegram chat app. |
| [MessageBird SMS](Nodes/Communication/MessageBirdSMS.md)                       | ![Symbol](Documentation/Flow/NodeSymbols/12.png) | Send an SMS to multipe people using the Messagebird API.                                        |
| [SendGrid e-mail](Nodes/Communication/SendGridEmail.md)                        | ![Symbol](Documentation/Flow/NodeSymbols/13.png) | Send an email to someone using the SendGrid API.                                                |
| [SendGrid Templated e-mail](Nodes/Communication/SendGridTemplated.md)          | ![Symbol](Documentation/Flow/NodeSymbols/13.png) | Send a Templated email to someone using the SendGrid API.                                       |
| **Expressions**                                                                |                                                  |                                                                                                 |
| [Boolean logic](Nodes/Expressions/Boolean%20Logic.md)                          | ![Symbol](Documentation/Flow/NodeSymbols/20.png) | A node for writing boolean logic.                                                               |
| [Expression](Nodes/Expressions/Expression.md)                                  | ![Symbol](Documentation/Flow/NodeSymbols/21.png) | A blank node to be used for a multitude of things.                                              |
| **Save**                                                                       |                                                  |                                                                                                 |
| [Load file data from Conneqt](Nodes/Save/LoadFileFromConneqt.md)               | ![Symbol](Documentation/Flow/NodeSymbols/31.png) | Load binary data from conneqt.                                                                  |
| [Save file data to Conneqt](Nodes/Save/SaveFileData.md)                        | ![Symbol](Documentation/Flow/NodeSymbols/32.png) | Save binary data to conneqt.                                                                    |
| [Save file from the web to Conneqt](Nodes/Save/SaveFileFromWeb.md)             | ![Symbol](Documentation/Flow/NodeSymbols/33.png) | Save a file from the web to conneqt using it's uri.                                             |
| **Navigation**                                                                 |                                                  |                                                                                                 |
| [Assing to asset](Nodes/Navigation/AssingToAsset.md)                           | ![Symbol](Documentation/Flow/NodeSymbols/40.png) | Have the flow be executed by another asset from this node onwards.                              |
| [Follow-up flow](Nodes/Navigation/RunFollowUpFlow.md)                          | ![Symbol](Documentation/Flow/NodeSymbols/41.png) | Start another flow after this one ends.                                                         |
| [Go to node](Nodes/Navigation/GoToNode.md)                                     | ![Symbol](Documentation/Flow/NodeSymbols/42.png) | Trace back the steps untill the specified node.                                                 |
| [Result action](Nodes/Navigation/ResultAction.md)                              | ![Symbol](Documentation/Flow/NodeSymbols/43.png) | Execute an action when the flow finishes.                                                       |
| [Result complex output](Nodes/Navigation/ResultComplexOutput.md)               | ![Symbol](Documentation/Flow/NodeSymbols/44.png) | Create a downloadable file when the flow finishes.                                              |
| [Result navigation](Nodes/Navigation/ResultNavigation.md)                      | ![Symbol](Documentation/Flow/NodeSymbols/45.png) | Open a dashboard, asset or flow when the flow finishes.                                         |
| [Run dynamic subflow](Nodes/Navigation/RunDynamicSubflow.md)                   | ![Symbol](Documentation/Flow/NodeSymbols/46.png) | Run a flow inside this flow. Inputs and outputs can be specified.                               |
| [Run subflow](Nodes/Navigation/RunSubflow.md)                                  | ![Symbol](Documentation/Flow/NodeSymbols/47.png) | Run a flow inside this flow.                                                                    |
| **Network**                                                                    |                                                  |                                                                                                 |
| [HTTP DELETE](Nodes/Network/HTTPDELETE.md)                                     | ![Symbol](Documentation/Flow/NodeSymbols/50.png) | Perfprms a HTTP DELETE request and returns the data.                                            |
| [HTTP GET](Nodes/Network/HTTPGET.md)                                           | ![Symbol](Documentation/Flow/NodeSymbols/51.png) | Perfprms a HTTP GET request and returns the data.                                               |
| [HTTP POST](Nodes/Network/HTTPPOST.md)                                         | ![Symbol](Documentation/Flow/NodeSymbols/52.png) | Perfprms a HTTP POST request and returns the data.                                              |
| [HTTP PUT](Nodes/Network/HTTPPUT.md)                                           | ![Symbol](Documentation/Flow/NodeSymbols/53.png) | Perfprms a HTTP PUT request and returns the data.                                               |
| **User Interface**                                                             |                                                  |                                                                                                 |
| [Button](Nodes/UserInterface/Button.md)                                        | ![Symbol](Documentation/Flow/NodeSymbols/60.png) | Displays a clickable button on the UI of the flow.                                              |
| [Checkbox](Nodes/UserInterface/Checkbox.md)                                    | ![Symbol](Documentation/Flow/NodeSymbols/61.png) | Displays a clickable checkbox on the UI of the flow.                                            |
| [Data grid](Nodes/UserInterface/DataGrid.md)                                   | ![Symbol](Documentation/Flow/NodeSymbols/62.png) | Displays a data grid on the UI of the flow.                                                     |
| [Date and time input](Nodes/UserInterface/DateAndTimeInput.md)                 | ![Symbol](Documentation/Flow/NodeSymbols/63.png) | Displays a date and time picker on te UI of the flow.                                           |
| [Date input](Nodes/UserInterface/DateInput.md)                                 | ![Symbol](Documentation/Flow/NodeSymbols/64.png) | Displays a date picker on the UI of the flow.                                                   |
| [Dropdown select list](Nodes/UserInterface/DropdownSelectList.md)              | ![Symbol](Documentation/Flow/NodeSymbols/65.png) | Displays a dropdown selection list on the UI of the flow.                                       |
| [Get geo-location](Nodes/UserInterface/GetGeoLocation.md)                      | ![Symbol](Documentation/Flow/NodeSymbols/66.png) | Retrieves the geo-location of the user.                                                         |
| [Image upload](Nodes/UserInterface/ImageUpload.md)                             | ![Symbol](Documentation/Flow/NodeSymbols/67.png) | Allows the user to upload an image.                                                             |
| [UI Navigate](Nodes/UserInterface/UINavigate.md)                               | ![Symbol](Documentation/Flow/NodeSymbols/68.png) | Displays a clickable button with a customizable notification badge.                             |
| [Navigate-maps](Nodes/UserInterface/NavigateLocation.md)                       | ![Symbol](Documentation/Flow/NodeSymbols/69.png) | Opens a navigation app and navigates to a specified location.                                   |
| [Numeric input](Nodes/UserInterface/NumericInput.md)                           | ![Symbol](Documentation/Flow/NodeSymbols/70.png) | Displays a numeric input field.                                                                 |
| [Popup message](Nodes/UserInterface/PopupMessage.md)                           | ![Symbol](Documentation/Flow/NodeSymbols/71.png) | Displays a popup message with clickable buttons.                                                |
| [Signature](Nodes/UserInterface/Signature.md)                                  | ![Symbol](Documentation/Flow/NodeSymbols/72.png) | Allows the user to add a signature.                                                             |
| [Text input](Nodes/UserInterface/TextInput.md)                                 | ![Symbol](Documentation/Flow/NodeSymbols/73.png) | Displays a textual input field.                                                                 |
| **Display**                                                                    |                                                  | Currently still found under `User interface`                                                    |
| [Clear controls from screen](Nodes/Display/ClearControls.md)                   | ![Symbol](Documentation/Flow/NodeSymbols/80.png) | Clears all UI element from the UI of the flow.                                                  |
| [Icon](Nodes/Display/Icon.md)                                                  | ![Symbol](Documentation/Flow/NodeSymbols/81.png) | Displays an icon with header on the UI of the flow.                                             |
| [Image](Nodes/Display/Image.md)                                                | ![Symbol](Documentation/Flow/NodeSymbols/82.png) | Displays an image on the UI of the flow.                                                        |
| [Textual information label](Nodes/Display/TextualInformationLabel.md)          | ![Symbol](Documentation/Flow/NodeSymbols/83.png) | Displays text on the UI of the flow.                                                            |
| [Textual label](Nodes/Display/Label.md)                                        | ![Symbol](Documentation/Flow/NodeSymbols/84.png) | Displays text and data on the UI of the flow.                                                   |
