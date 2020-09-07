## OAuth with Keycloak

Use Keycloak as identity provider

TGIF, DKRZ, 11 September 2020

<img height="50" src="media/cc-license.png" alt="Creative Commons License"/>
---
## OAuth

https://www.oauth.com/
---
## Keycloak

* Open Source Identity and Access Management
* Secure your Services ... handle users.
* Manage login to Portals.
* Protect resources: downloading in ESGF, access to processing.
* Supports OAuth2.
* https://www.keycloak.org/
---
## Keycloak for ESGF
<img height="400" src="media/keycloak-realms.png" alt="Keycloak Realms"/>
---
## Protect a Portal
https://demo-phoenix.cloud.dkrz.de/
<img height="300" src="media/keycloak-sign-in.png" alt="Keycloak Sign-in"/>
* OAuth authorization code grant workflow
* redirection-based flow
```note
https://github.com/oauthlib/oauthlib

A client utilizing the authorization code grant workflow.

A web application is a confidential client running on a web server. Resource owners access the client via an HTML user interface rendered in a user-agent on the device used by the resource owner. The client credentials as well as any access token issued to the client are stored on the web server and are not exposed to or accessible by the resource owner.

The authorization code grant type is used to obtain both access tokens and refresh tokens and is optimized for confidential clients. As a redirection-based flow, the client must be capable of interacting with the resource owner’s user-agent (typically a web browser) and capable of receiving incoming requests (via redirection) from the authorization server.
```
---
## Protect a Resource
Web Processing Service with token based access
<img height="300" src="media/wps-protected.png" alt="WPS protected"/>
---
## Use an Access Token
<img height="300" src="media/access-token.png" alt="Access Token"/>
Use a string token valid for a short time
---
## Get a Token without redirect
<img height="280" src="media/keycloak-backend-client.png" alt="Keycload Backend Client"/>
* OAuth client credentials grant workflow
* From terminal or Jupyter notebook
```note
A public client utilizing the client credentials grant workflow.

The client can request an access token using only its client credentials (or other supported means of authentication) when the client is requesting access to the protected resources under its control, or those of another resource owner which has been previously arranged with the authorization server (the method of which is beyond the scope of this specification).

The client credentials grant type MUST only be used by confidential clients.

Since the client authentication is used as the authorization grant, no additional authorization request is needed.
```
---
## Use Token to access Resource
Add token in header variable "Bearer" to access resource
<img height="300" src="media/birdy-example-with-token.png" alt="birdy with token"/>
