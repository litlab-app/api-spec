Delete Category
---------------
The Delete Category call is to be used by LitLab admins in order to remove a category. This action cannot be undone.

###Endpoint
Use the following endpoint to access this operation:

Request Method: `DELETE`

	{platform}/{version}/admin/cat/{catId}

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |
| catId          | Integer     | Required     | Specifies the ID ( as returned by [Categories][] API ) of the category to be Modified       |

###Request Body
The Delete Category request has no body.

####Request Header Fields
The Request header specifies input about the request

| Field          | Type        | Use          | Description                                                                   |
|:---------------|:------------|:-------------|:------------------------------------------------------------------------------|
| sessionId      | String      | Required     | Specifies the LitLab session of the admin trying to delete the category       | 

###Response
The Delete Category JSON response has this form:

	{
	    "success": true
	}

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                |
|:---------------|:------------|:-----------------------------------------------------------|
| success        | Boolean     | Specifies whether category was deleted successfully        | 

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String      | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.        |
| _Error_.Message | String      | Provides a human readable explanation of the status.                                                             |

[ErrorCodes]: ../../appendix/ErrorCodes.md
