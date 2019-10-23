Get User
----------
The Get User call returns the details of the specified LitLab User.

###Endpoint
Use the following endpoint to access this operation:

Request Method: `GET`

	{platform}/{version}/admin/user

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |

###Request Body
    The Get User request has no body

####Request Header Fields
The Request header specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| sessionId      | String      | Required     | Specifies the LitLab session granted to current user for authentication           | 


###Response
The Get User JSON response has this form:

	{
	    "name": "Full Name",
	    "email": "username@domain.com"
	}

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                        |
|:---------------|:------------|:-------------------------------------------------------------------|
| name           | String      | Specifies the full name of the current user                        |
| email          | String      | Specifies the registered email address of the user                 |

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String      | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.        |
| _Error_.Message | String      | Provides a human readable explanation of the status.                                                             |

[ErrorCodes]: ../../appendix/ErrorCodes.md
