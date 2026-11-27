## Project Overview
Conceptualize and understand SAML/OIDC login flows.
## The SAML Flow
1. User attempts to login to an application.
2. The application redirects user to an IdP with an authentication request.
3. The IdP authenticates the user.
4. The IdP responds with a signed assertion containing claims about the user's identity.
5. The application processes and validates the assertion.
6. The application starts a session for the user.

## The OpenID Connect Flow
1. User attempts to login to an application.
2. The application redirects user to an IdP with an authentication request.
3. The IdP authenticates the user.
4. The IdP responds to the application with an authorization code.
5. The application exchanges the authorization code at the IdP's token endpoint, over a back channel, to obtain the signed ID token. 
7. The application processes the ID token to establish who signed in.
8. The application creates a session and sends the browser a session cookie.

## How They Compare
Both protocols enable single sign on and prevent users from sharing credentials with various applications.
Both involve configurations made in IdP and SP systems to establish the trust relationship.
Both result in session creation.

## Where Trust Comes From
Configurations made in IdP and SP systems.

## What Goes Wrong
Stolen assertions/tokens and sessions can result in unauthorized access.

## Security Lessons Learned
Trust is established by administrators configuring IdP and Service Provider systems. Setting this up allows users to login once, and
receive access to various applications. These applications can grant this access without being entitled or storing the user's credentials.
Essentially, storing and validating credentials became a completely separate job the Service Provider's do not need to implement themselves.

## Future Improvements
Polishing the diagram drafts.
Decoding a token via jwt.io or jwt.ms
Configure trust between an IdP and an SP.
