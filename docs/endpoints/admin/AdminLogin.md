Admin Login
------
The Login call authenticates a LitLab admin user and returns a LitLab API admin session to the user.

###Endpoint
Use the following endpoint to access this operation: 

Request Method: `POST`

	{platform}/{version}/admin/login

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |

###Request Body
The Admin Login JSON request body has this form:

    {
        "email": "username@domain.com",
        "encryption": "YmVkODE2M420MmUyZjRmY2FmYjBhN2MyNzkwYzk0NjYzODg0M2MxYTY1NGFiMWU1N2UzNGVlNDFmNWM4ZWYxNw==",
        "gcaptcha": "Google captcha response"
    }

####Request Body Fields
The Request Body specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| email          | String      | Required     | Specifies the e-mail user used to register with LitLab. It serves as the username        | 
| encryption     | String      | Required     | Password granted to the Admin user      |
| gcaptcha       | String      | Required     | Response received by client while confirming being not a robot to be verified at server  |

###Response
The Login JSON response has this form:

	{
	    "sessionId": "5f2a9fb6-c077-4dda-b71f-835035247916"
	}

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                |
|:---------------|:------------|:-----------------------------------------------------------|
| sessionId      | String      | Specifies the ID of the unique session granted to the user | 

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String      | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.        |
| _Error_.Message | String      | Provides a human readable explanation of the status.                                                             |

[ErrorCodes]: ../../appendix/ErrorCodes.md
