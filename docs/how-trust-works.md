# Administrators Establish Trust Relationships Between Systems

## Partial SSO Setup in Entra ID for an Application
![EntraID Enterprise App SSO Setup](/images/SSO_Config_EntraID.png)

## What Entra ID Needs to Know
- Section 1 contains an identifier for the Service Provider (app) and a reply URL to route IdP responses. 
- Section 2 defines the attributes and claims the IdP will share with the Service Provider. 
- Section 3 contains certificate information so the IdP can sign assertions.
- Section 4 contains additional information that admins must configure on the Service Provider to establish this trust relationship.

## Security Considerations
After a successful SAML or OIDC sign-in, the IdP issues a bearer token that user-agents can present to 
create a session with the receiving Service Provider. 

Anyone who obtains and presents a valid copy of this token may be able to access the service as the authenticated user.

## Protections
- This is why every step in these flows rely on TLS to protect against token and session cookie interception. 
- Tokens are also short-lived to minimize the length of time a compromised or revoked token remains valid. 
- Applications also check that tokens/assertions are meant for them. Attackers cannot simply reuse a token/assertion for
another application that may trust the same IdP.
- Applications must check the assertion/token signatures to ensure they come from the IdP they've been configured to trust.
- MFA helps prevent attackers from signing in and obtaining IdP-issued tokens.
It does not, by itself, prevent them from using stolen tokens or session cookies.
