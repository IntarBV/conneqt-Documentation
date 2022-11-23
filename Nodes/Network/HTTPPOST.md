# HTTP POST

Performs a synchronous HTTP POST to a url and returns the data in the result of this node. A HTTP POST request is used to create a resource. The difference between PUT and POST is that calling PUT multiple times will result in the same result. Calling POST multiple times will have the side effects of creating multiple of the same resource.

### Node

##### Url

The URL for the HTTP POST. E.g. https://example.org/api/can?id=12

##### Data

The data to post. Currently only JSON objects are supported.
