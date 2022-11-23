# An introduction to conneqt variables and arrays

### Variables

This short explanation covers most of the coding knowledge neccesary to use conneqt. This mostly concerns the way variables are named and what they can store.

Variables are just as the name suggests, things that can be changed. A variable stores some data that can be accessed or changed by the code. Asset properties for example are variables. But because of the coding language conneqt was written in, not all kinds of data can be stored in any variable. Instead there are variable types. Some of these are common accros languages, and thus also used by conneqt:

| Type           | Stores                                         |
| -------------- | ---------------------------------------------- |
| String         | Text, denoted between quotation marks `"Text"` |
| Integer        | Whole numbers                                  |
| Floats         | Floating point/Decimal numbers                 |
| Bools/Booleans | True/False statements                          |

Furthermore, conneqt has some custom variables of its own:

| Type                     | stores                                                                        | based on    |
| ------------------------ | ----------------------------------------------------------------------------- | ----------- |
| Icon                     | An icon                                                                       | A string    |
| Date and time            | A date and a time, if only a date is specified it will save the time as 22:00 | A string    |
| Placed inside            | The higherarcial location of the asset                                        | A string    |
| In areas                 | A list of area variables                                                      | An array    |
| Area                     | A zone on a map                                                               | An array    |
| Location                 | A coordinate                                                                  | An array    |
| Asset                    | A single asset                                                                | An object   |
| Assettype                | An Asset type                                                                 | A class     |
| Flow reference / trigger | A reference to a flow                                                         | A reference |

### Arrays

Besides variables, arrays are also an important part of coding and are used within conneqt. An array is a list of variables. It is denoted by first having a variable name, folowed by square brackets: `exampleArray[]`. Specific variables in this list are accessed with their index number. However, it is important to know that this index number stars counting from 0: `exampleArray[0]` is the first item in the list, `exampleArray[1]` the seccond, etc. This list can only be made up from variables of the same kind within conneqt. Thus we cannot have `exampleArray[0]` be `"ExampleString"` and `exampleArray[1]` be `4`. To use conneqt, it is not neseccary to know how to create arrays, conneqt will do this for you. However, to make proper use of node referencing, it is advantageous to know how they work.
