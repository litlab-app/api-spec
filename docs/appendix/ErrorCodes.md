Appendix A: LitLab Error Codes
-------------------------------------
The recognised Error codes are:

| Code    | Description                                          													|
|:--------|:--------------------------------------------------------------------------------------------------------|
| 1001	  | General Error: Indicates that the error at server does not fit into any specific recognised category as defined below |
| 1002	  | Authentication Error: Indicates that the request could not be fulfilled because of authentication failure |
| 1003	  | Invalid JSON Error: Indicates that the input parameters are not received as a valid JSON |
| 1004	  | Invalid Client Error: Indicates that the client in unknown or invalid to access the APIs  |
| 1005	  | Missing Session ID Error: Indicates that a request has been made without the session ID where a session is mandatory |
| 1006	  | Invalid Session Error: Indicates that a request has been made with an expired or invalid session ID |
| 1007	  | Access Denied Error: Indicates that the client has been denied access to the requested information |
| 1008	  | No Match Error: Indicates that the input parameters do not match a field based on which information / action is requested  |
| 1009	  | Invalid Request Error: Indicates that the request has been made without some mandatory inputs or in invalid format |
| 1010	  | Missing Activation Code Error: Indicates that an account activation request has been made without sending the activation code |
| 1011	  | Invalid Activation Code Error: Indicates that an account activation request has been made with invalid activation code |
| 1012	  | Invalid Encryption Error: Indicates that the input parameters are incorrectly encrypted / hashed |
| 1013	  | Duplicate Email Error: Indicates that a new registration is requested by an existing LitLab User |
| 1014	  | Inactive Account Error: Indicates that a session is requested by an inactive account holder |
| 1015	  | Suspended Account Error: Indicates that a session is requested by a suspended account holder |


For detailed information on the specific case of error read the _Error_ header field
