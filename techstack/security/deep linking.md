#security #oauth #mobile

When mobile app are using [[OAuth 2.0]] a problem arises: The OAuth server sends the response to the authorization back to a [[URL]], which in mobiles are done now by deep linking to prevent sneaking/stealing.
An app provider needs to provide truth of owning the domain, before he can reroute any call to an endpoint [[URL]] on the mobile to his own app (what's deep linking is all about).

Here [[PKCE]] is another helpful concept.
