Get LitLab categories
------------------------
The Get Categories call returns all the default LitLab category filters

###Endpoint
Use the following endpoint to access this operation:

Request Method: `GET`

	{platform}/{version}/app/cats

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |

###Request Body
The Get Categories request has no body

####Request Header Fields
The Request header specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| sessionId      | String      | Optional     | Specifies the LitLab session to return categories of current user only. If this field is not provided it returns all the available LitLab categories | 


###Response
The Get Categories JSON response has this form:

    {
    	"cats": [{
    		"name": "Molecular and Cellular",
    		"id": 1,
    		"isSub": true
    	}, 
    	:
    	:
    	:
    	, {
    		"subs": [17, 18, 19],
    		"name": "Host organisation",
    		"id": 20,
    		"isSub": false
    	}],
    	"count": 20
    }

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                                               |
|:---------------|:------------|:------------------------------------------------------------------------------------------|
| cats           | JSON Array  | Contains an array of JSON objects specifying the categories                               |
| name           | String      | Specifies the name of the category                                                        | 
| id             | Integer     | Specifies the unique ID of the category                                                   | 
| isSub          | Boolean     | Specifies whether this category is a sub-category. False signifies it is a main category  | 
| subs           | Int Array   | Specifies the IDs of sub categories of this category                                      | 
| count          | Integer     | Specifies the total number of categories returned                                         | 

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String      | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.        |
| _Error_.Message | String      | Provides a human readable explanation of the status.                                                             |

[ErrorCodes]: ../../appendix/ErrorCodes.md
