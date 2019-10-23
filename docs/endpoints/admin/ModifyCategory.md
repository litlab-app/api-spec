Modify LitLab Filter Category
-----------------------------
The Modify Category call is used to make edits to the pre-defined categories by an admin. 

###Endpoint
Use the following endpoint to access this operation:

Request Method: `POST`

	{platform}/{version}/admin/cat/{catId}

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |
| catId          | Integer     | Required     | Specifies the ID ( as returned by [Categories][] API ) of the category to be Modified       |


###Request Body
The Modify category JSON request body has this form:

    {
        "name": "category name",
        "subs": "2,3",
        "isSub": true
    }

####Request Body Fields
The Request Body specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| name           | String      | Optional     | Modified name for the category                                                            |
| subs           | String      | Optional     | Modified comma separated list of sub categories of this category                          |
| isSub          | Boolean     | Optional     | Modified value of this category being a sub category of any other category                |

###Response
The Modified Category JSON response has this form:

    {
        "subs": [17, 18, 19],
        "name": "Host organisation",
        "id": 20,
        "isSub": false
    }

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field     | Type      | Description                                                                                            |
|:----------|:----------|:-------------------------------------------------------------------------------------------------------|
| subs      | Int Array | Specifies the Modified list of sub-categories. Details of each to be obtained using [Categories][] APIs |
| name      | String    | Specifies the Modified name of the category                                                             |
| id        | Integer   | Specifies the unique ID of the Modified category                                                        |
| isSub     | Boolean   | Specifies whether Modified category is a sub-category for any other category                            |

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String       | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.         |
| _Error_.Message | String       | Provides a human readable explanation of the status.                                                             |

[ErrorCodes]: ../../appendix/ErrorCodes.md
[Categories]: ../application/GetCategories.md
