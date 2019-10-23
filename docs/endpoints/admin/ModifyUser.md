Modify LitLab User
---------------
The Modify User call is used to make edits to the LitLab user by an admin. Everything except the e-mail / username can be edited by the admin user. 

###Endpoint
Use the following endpoint to access this operation:

Request Method: `POST`

	{platform}/{version}/admin/user/{userId}/{userKey}

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |
| userId         | Integer     | Required     | Specifies the ID ( as returned by [Search User][] API ) of the user to be Modified       |
| userKey        | String      | Required     | Specifies the unique key ( as returned by [Search User][] API ) associated with the user         |

###Request Body
The Modify user JSON request body has this form:

    {
        "forename": "First",
        "surname": "Second",
        "status": "Suspended",
        "type": "Beta"
    }

####Request Body Fields
The Request Body specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| forename       | String      | Optional    | Modified first name(s) of the user      |
| surname        | String      | Optional    | Modified last name of the user      |
| status         | String      | Optional    | Modified status for the user. Valid values = New / Active / Suspended       |
| type           | String      | Optional    | Modified type of the user. Valid values = Admin / Alpha / Beta / Test / Regular       |

###Response
The Modify User JSON response has this form:

	{
	    "forename": "First",
	    "surname": "Second",
	    "email": "username@domain.com",
	    "type": "Beta",
	    "status": "Suspended"
	}

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                                                     |
|:---------------|:------------|:------------------------------------------------------------------------------------------------|
| forename      | String       | Specifies the forename of the Modified user                                                     |
| surname       | String       | Specifies the surname of the Modified user                                                      |
| email         | String       | Specifies the email of the Modified user. This serves as the unique username for Login requests |
| type          | String       | Specifies the type of Modified user                                                             |
| status        | String       | Specifies the status of Modified user                                                           |

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String       | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.         |
| _Error_.Message | String       | Provides a human readable explanation of the status.                                                             |

[ErrorCodes]: ../../appendix/ErrorCodes.md
[Search User]: SearchUser.md
