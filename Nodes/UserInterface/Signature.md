# Signature

Presents the user with a drawing screen. Can be used for signatures, quick sketches etc.

### Node properties

##### Label

Text above the area that the user can draw in.

##### Mandatory

Denotes if the user is mandated to supply a signature.

### Referencing

The node returns 5 values:

| Value           | Returns                                                                                                                                                |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ContentType     | Returns the type of content and the way it's saved.                                                                                                    |
| Size            | Returns the size of the file in bytes.                                                                                                                 |
| Base64Thumbnail | Returns the image in a Base64 encryption. This is the return data you want to reference to use the image.                                              |
| Identifier      | Returns the identifier under which the file is stored in the database. This is the return data you want to copy to reference the file in another flow. |
| Name            | Returns the name of the image.                                                                                                                         |

### Output:

The ‘any result’ is triggered as soon as the drawer lets go. It is recommended to use a button connected to the green dot if the drawer has to be able to place multiple lines.

# Example:

[Create account (add avatar)](../../Nodes/Examples/CreateAccount.md)
