# HTTP PUT

Performs a synchronous HTTP PUT to a url and returns the data in the result of this node. A HTTP PUT request is used to create or update a resource. The difference between PUT and POST is that calling PUT multiple times will result in the same result. Calling POST multiple times will have the side effects of creating multiple of the same resource.

### Node properties

##### Url

The URL for the HTTP PUT. E.g. https://example.org/api/can?id=12

##### Data

The data to put. Currently only JSON objects are supported.
