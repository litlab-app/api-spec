Modify Funding Opportunity
---------
The Modify Opportunity call is to modify funding opportunities registered on Litlab. This action can only be performed by Admins

###Endpoint
Use the following endpoint to access this operation:

Request Method: `POST`

	{platform}/{version}/admin/opp/{oppId}

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |
| oppId          | Integer     | Required     | Specifies the unique ID of opportunity registered on Litlab database to be modified         |

###Request Body
The Modify user JSON request body has this form:

    {
        "duration": "First",
        "text": "Second",
        "title": "Suspended",
        "fund": "Beta",
        "host": ""
    }

####Request Body Fields
The Request Body specifies input about the request

| Field          | Type        | Use         | Description                                   |
|:---------------|:------------|:------------|:----------------------------------------------|
| duration       | String      | Optional    | Modified duration of the opportunity          |
| text           | String      | Optional    | Modified description of the opportunity       |
| title          | String      | Optional    | Modified title of the opportunity             |
| fund           | String      | Optional    | Modified funding detail of the opportunity    |
| host           | String      | Optional    | Modified host organisation of the opportunity |


####Request Header Fields
The Request header specifies input about the request

| Field          | Type        | Use          | Description                                      |
|:---------------|:------------|:-------------|:-------------------------------------------------|
| sessionId      | String      | Required     | Specifies an active LitLab Admin session         | 

###Response
The Modify Opportunity JSON response has this form:

    {
        "opp": {
            "duration": "4 years",
            "res": [5, 9],
            "fdetail": "£300,000, including salary, fellowship supplement and research expenses",
            "award": [11],
            "clo": "2019-09-05",
            "host": "-",
            "id": 1,
            "text": "Offering recently qualified postdoctoral researchers the opportunity to start independent research careers, working in some of the best research environments in the world.",
            "title": "Sir Henry Wellcome Postdoctoral Fellowships"
        }
    }

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                                                     |
|:---------------|:------------|:------------------------------------------------------------------------------------------------|
| opp            | Json Object | Contains the updated details of the opportunity                                                 |
| res            | Int Array   | Specifies the Research Area of the opportunity. Details of each found with [Categories API][]   |
| fdetail        | String      | Specifies the Funding details of the opportunity                                                |
| award          | Int Array   | Specifies the Award Type of the opportunity.  Details of each found with [Categories API][]     |
| clo            | String      | Specifies the clsoing date of the funding opportunity                                           |
| host           | String      | Specifies the host organisation of the opportunity                                              |
| id             | Integer     | Specifies the unique ID of opportunity registered on Litlab database                            |
| text           | String      | Specifies the description of the opportunity                                                    |
| title          | String      | Specifies the title of the opportunity                                                          |
| duration       | String      | Specifies the duration of funding                                                               |

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String      | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.          |
| _Error_.Message | String      | Provides a human readable explanation of the status.                                                              |

[ErrorCodes]: ../../appendix/ErrorCodes.md
[Categories API]: ../application/GetCategories.md