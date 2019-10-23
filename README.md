LitLab API
========================
LitLab APIs specified in this document are built RESTful - the default format of inputs and outputs are JSON, unless specified differently. With these API endpoints, you can fully integrate litlab services into your web / android / iOS applications, control, customize and scale as you like.

While integrating you would notice that all our APIs expect a {platform} and a {ver}sion parameter in the request URI. In order to get customised results for different platforms use this field. It could presently take only 'android', 'ios', and 'web' as valid values, but we are working on adding more platform sizes and compliance soon. This is made highly configurable with an intention that we return customised response formats to different kind of platforms. Also, this helps our programmers to segregate the monitoring logs for different clients. If you need it for any other platform than specified please contact us.

{ver} defines the API version. All APIs are built on version basis - so an old client might want to stick with an older API version while others may opt to upgrade to the latest version to get easier, faster access to some data or more customised JSON response. This being our very first release, it requires clients to be set at version 1.


##Steps to Get Started
1. [Reach out to us](mailto:cto@litlab.app?subject=[GitHub]%20Source%20Litlab%20Admin) to get your API credentials
2. Familiarize yourself with the [Basic Concepts](#basic-concepts) and the API operations.
3. Begin developing your application!

We will reach out to you concerning commercialization of your application.

##Endpoints

###Admin operations
- **[<code>POST</code> Login](docs/endpoints/admin/AdminLogin.md)**
- **[<code>GET</code> Admin User](docs/endpoints/admin/GetAdminUser.md)**
- **[<code>GET</code> All Categories](docs/endpoints/application/GetCategories.md)**
- **[<code>PUT</code> Add New Category](docs/endpoints/admin/AddCategory.md)**
- **[<code>POST</code> Modify Category](docs/endpoints/admin/ModifyCategory.md)**
- **[<code>DELETE</code> Delete Category](docs/endpoints/admin/DeleteCategory.md)**
- **[<code>GET</code> Search User](docs/endpoints/admin/SearchUser.md)**
- **[<code>POST</code> Modify User](docs/endpoints/admin/ModifyUser.md)**
- **[<code>GET</code> Search Opportunity](docs/endpoints/admin/SearchOpportunity.md)**
- **[<code>POST</code> Modify Opportunity](docs/endpoints/admin/ModifyOpportunity.md)**
- **[<code>PUT</code> Logout](docs/endpoints/auth/Logout.md)**

###Application operations
- **[<code>GET</code> GetCategories](docs/endpoints/application/GetCategories.md)**


##Basic Concepts

###Authentication
All operations in the LitLab APIs require a session ID argument provided in the RequestHeader. 
Authorization is granted and a session ID based on application and user credentials. 
The session ID securely identifies the caller of an operation. When called, an operation checks the validity of the session ID before executing the request. 
A malformed, invalid, or expired token causes an operation to fail.

Clients get session ID by authenticating themselves using the [Login API](docs/endpoints/auth/Login.md).

###Password Encryption Operations
By default, no password is stored on litlab databases rather a PBKDF2 encryption is stored to prevent passwords being hacked by attackers.
While doing password related operations the clients must first get the current PBKDF2 encoding settings on LitLab from the [Encoding API](docs/endpoints/auth/Encoding.md).
Using the provided settings, the client must generate a salt of given length in lowercase using only hex characters. Using the given iteration count, generated salt and 256 bit key length the user password must be hashed in PBKDF2. This generated hash must be Base-64 encoded to be used with the API endpoints.  

###Session Expiration and Renewal
Session ID expires after 14 days of inactivity so that the App users are not forced to login every time they launch the App. Depending on the user actions this setting may vary. 

On expiry the API returns specific error code and message to the client, and they must use the [Login API](docs/endpoints/auth/Login.md) to request a new session ID. 