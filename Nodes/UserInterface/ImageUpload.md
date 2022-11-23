# Image upload

Allows the user to upload a picture.

### Node properties

##### Label

The text above the choose file button.

##### Background

Sets the background color of the 'upload' button.

##### Size

Allows for compression of the image by reducing its pixel surface.

##### Mandatory

When checked, uploading a picture becomes mandatory.

### Referencing

The node returns 5 values:

| Value           | Returns                                                                                                                                                |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ContentType     | Returns the type of content and the way it's saved.                                                                                                    |
| Size            | Returns the size of the file in bytes.                                                                                                                 |
| Base64Thumbnail | Returns the image in a Base64 encryption. This is the return data you want to reference to use the image.                                              |
| Identifier      | Returns the identifier under which the file is stored in the database. This is the return data you want to copy to reference the file in another flow. |
| Name            | Returns the name of the image.                                                                                                                         |

# Examples:

[Using an image](../../Nodes/Examples/UsingAnImage.md)

[Create account (add avatar)](../../Nodes/Examples/CreateAccount.md)
