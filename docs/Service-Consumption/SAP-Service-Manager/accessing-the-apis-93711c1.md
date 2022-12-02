<!-- loio93711c15d9c74efe9e359a7f9730f929 -->

# Accessing the APIs

You can access the SAP Service Manager service APIs with a valid OAuth2 access token. The API access level \(read/write\) and the allowed API endpoints are controlled by the access token scopes.

There are two methods of obtaining access tokens:

-   User Access Tokens – represents a named user. The included scopes are derived from the user's roles. See [User Access](user-access-37f0e7e.md).

-   Client Access Tokens – represents a technical client. Such tokens are retrieved using OAuth client credentials provided by instances of the service-manager service. The included scopes are determined by the used service plan. See [Technical Access](technical-access-666dfdc.md).


-   **[User Access](user-access-37f0e7e.md "The SAP Service
                                Manager
		API can be accessed using OAuth 2.0 access tokens issued for named users, which have the
		proper roles assigned to them. ")**  
The SAP Service Manager API can be accessed using OAuth 2.0 access tokens issued for named users, which have the proper roles assigned to them.
-   **[Technical Access](technical-access-666dfdc.md "The SAP Service
                                Manager API
		can be accessed using OAuth 2.0 access tokens issued for technical clients by providing the
		client credentials (ID and secret). ")**  
The SAP Service Manager API can be accessed using OAuth 2.0 access tokens issued for technical clients by providing the client credentials \(ID and secret\).

