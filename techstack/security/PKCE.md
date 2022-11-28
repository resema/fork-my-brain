#security #mobile #oauth 

### Proof Key for Code Exchange 

PKCE ([RFC 7636](http://tools.ietf.org/html/rfc7636)) is an extension to the [Authorization Code flow](https://oauth.net/2/grant-types/authorization-code/) to prevent [[CSRF]] and authorization code injection attacks.

PKCE is _not_ a replacement for a client secret, and PKCE is recommended even if a client is using a client secret.

Note: Because PKCE is not a replacement for client authentication, it does _not_ allow treating a public client as a confidential client.

PKCE was originally designed to protect the authorization code flow in mobile apps, but its ability to prevent authorization code injection makes it useful for every type of OAuth client, even web apps that use a client secret.