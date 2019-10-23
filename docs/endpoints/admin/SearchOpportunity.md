Search Funding Opportunity
---------
The Search Opportunity call is to search for funding opportunities registered on Litlab. Opportunity search can be performed only by an admin and will later be used by users themselves

###Endpoint
Use the following endpoint to access this operation:

Request Method: `GET`

	{platform}/{version}/admin/search/opp

###Request Path Fields
The Request Path fields specifies input about the request

| Field          | Type        | Use          | Description                                                                                        |
|:---------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------|
| platform       | String      | Required     | Specifies the client platform making the request to receive customised response for given platform |
| version        | String      | Required     | Specifies the client version making the request to receive response based on given version         |
| q              | String      | Required     | Query parameter which will be searched in the various fields of user table         |

###Request Body
The Search Opportunity request has no body.

####Request Header Fields
The Request header specifies input about the request

| Field          | Type        | Use          | Description                                                                              |
|:---------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| sessionId      | String      | Required     | Specifies an active LitLab Admin session                                                 | 

###Response
The Search Opportunity JSON response has this form:

    {
        "opps": [{
            "duration": "3 years",
            "res": [3, 9],
            "fdetail": "Up to £3.3 million, will not cover capital items in the UK",
            "award": [12, 13],
            "clo": "2019-09-05",
            "host": null,
            "id": 2,
            "text": "This initiative will provide funding for high quality collaborative research partnerships focused on addressing the growing global burden of antimicrobial resistance, specifically antibacterial resistance in (South) Africa, through drug discovery.",
            "title": "South Africa-UK Antibiotic Accelerator Initiative"
        }, {
            "duration": "1-3 years",
            "res": [2, 6],
            "fdetail": "Typically £100,000 per annum",
            "award": [12],
            "clo": "2019-10-10",
            "host": null,
            "id": 3,
            "text": "This scheme from CRUK funds projects at any stage of drug discovery, from target (pathway) identification and validation to early preclinical studies. Awards can support early stage translational research with a clear pathway towards further biotherapeutic development.",
            "title": "Biotherapeutic Drug Discovery Grant"
        }],
        "count": 2
    }

####Response Body Fields
The response Body contains the result of the operation carried out by the server

| Field          | Type        | Description                                                                                     |
|:---------------|:------------|:------------------------------------------------------------------------------------------------|
| count          | Integer     | Specifies the number of opportunities returned for a given search                               |
| opps           | Json Array  | Contains the details of the opportunities returned for the search                               |
| res            | Int Array   | Specifies the Research Area of the opportunity. Details of each found with [Categories API][]   |
| fdetail        | String      | Specifies the Funding details of the opportunity                                                |
| award          | Int Array   | Specifies the Award Type of the opportunity.  Details of each found with [Categories API][]     |
| clo            | String      | Specifies the clsoing date of the funding opportunity                                           |
| host           | String      | Specifies the host organisation of the opportunity                                              |
| id             | Integer     | Specifies the unique ID of opportunity registered on Litlab database                            |
| text           | String      | Specifies the description of the opportunity                                                    |
| title          | String      | Specifies the title of the opportunity                                                          |

####Response Header Fields
The Response Header returns additional information about the operation execution and response.

| Field            | Type        | Description                                                                                                      |
|:-----------------|:------------|:-----------------------------------------------------------------------------------------------------------------|
| _Error_.Code    | String      | Identifies the category of the status notification. See [ErrorCodes][] for an explanations of the codes.          |
| _Error_.Message | String      | Provides a human readable explanation of the status.                                                              |

[ErrorCodes]: ../../appendix/ErrorCodes.md
[Categories API]: ../application/GetCategories.md