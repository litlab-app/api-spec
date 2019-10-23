Add New Category
-----------------------------
The Add New Category call is used to create a new category by an admin 

###Endpoint
Use the following endpoint to access this operation:

Request Method: `PUT`

	{platform}/{version}/admin/cat

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |


###Request Body
The Add Category JSON request body has this form:

    {
        "name": "category name",
        "subs": "2,3",
        "isSub": true
    }

####Request Body Fields
The Request Body specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| name           | String      | Optional     | Name for the category                                                            |
| subs           | String      | Optional     | Comma separated list of sub categories of this category                          |
| isSub          | Boolean     | Optional     | Specifies whether it is a sub category of any other category                |

###Response
The Add Category JSON response has this form:

    {
        "subs": [2, 7, 8],
        "name": "New Category",
        "id": 22,
        "isSub": true
    }

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field     | Type      | Description                                                                                            |
|:----------|:----------|:-------------------------------------------------------------------------------------------------------|
| subs      | Int Array | Specifies the list of sub-categories. Details of each to be obtained using [Categories][] APIs |
| name      | String    | Specifies the name of the category                                                             |
| id        | Integer   | Specifies the unique ID of the category                                                        |
| isSub     | Boolean   | Specifies whether this category is a sub-category for any other category                            |

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String       | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.         |
| _Error_.Message | String       | Provides a human readable explanation of the status.                                                             |

[ErrorCodes]: ../../appendix/ErrorCodes.md
[Categories]: ../application/GetCategories.md
