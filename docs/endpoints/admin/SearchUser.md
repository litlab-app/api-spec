Search User
---------
The Search User call is to search for registered users on Litlab. Users register on Litlab using [Registration APIs][]. User search can be performed only by an admin.

###Endpoint
Use the following endpoint to access this operation:

Request Method: `GET`

	{platform}/{version}/admin/search/user

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |
| q              | String      | Required     | Query parameter which will be searched in the various fields of user table         |

###Request Body
The Search User request has no body.

####Request Header Fields
The Request header specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| sessionId      | String      | Required     | Specifies an active LitLab Admin session                                                 | 

###Response
The Search User JSON response has this form:

    {
        "count": 2,
        "users": [{
            "forename": "First",
            "surname": "Last",
            "id": 1,
            "type": "ADMIN",
            "email": "userone@domain.com",
            "key": "Nc5x6AMKYwjw",
            "status": "ACTIVE",
            "apps": "<p>1. Submitted: 2019-09-23, Modified: 2019-09-23, Funding Bodies: [1], Current Status: closed. </p><p>2. Submitted: 2019-09-23, Modified: 2019-09-23, Funding Bodies: [1, 2], Current Status: open. </p><p>3. Submitted: 2019-09-23, Modified: 2019-09-23, Funding Bodies: [1, 2, 3], Current Status: open. </p>"
        }, {
            "forename": "Second",
            "surname": "Last",
            "id": 2,
            "type": "REGULAR",
            "email": "usertwo@domain.com",
            "key": "baytx2miWAT3",
            "status": "ACTIVE",
            "apps": "<p>4. Submitted: 2019-09-23, Modified: 2019-09-23, Funding Bodies: [4], Current Status: closed. </p>"
        }]
    }

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                                                     |
|:---------------|:------------|:------------------------------------------------------------------------------------------------|
| count          | Integer     | Specifies the number of users returned for a given search                                       |
| users          | Json Array  | Contains the details of the users returned for the search                                       |
| forename       | String      | Specifies the forename of the user                                                              |
| surname        | String      | Specifies the surname of the user                                                               |
| id             | Integer     | Specifies the unique ID of the user on Litlab database                                          |
| type           | String      | Specifies the type of the registered user. Valid values = Admin / Alpha / Beta / Test / Regular |
| email          | String      | Specifies the email / username of the user                                                      |
| key            | String      | Specifies the unique key of user                                                                |
| status         | String      | Specifies the status of user. Valid values = New / Active / Suspended                           |
| apps           | String(HTML)| Lists the applications submitted by the user                                                    |

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String      | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.          |
| _Error_.Message | String      | Provides a human readable explanation of the status.                                                              |

[ErrorCodes]: ../../appendix/ErrorCodes.md
[Registration APIs]: ../auth/Register.md