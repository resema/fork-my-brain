#security #token #refreshtoken #oauth 

Are refresh token can be used behind the scene to refresh the [token](/token) for access with the interaction of the user with [OAuth 2.0](/techstack/security/OAuth%202.0.md) server.

In mobile this `refresh_token` is stored in a sandbox like storage, not even accessable by the app itself.

```json
{
	"token_type": "Bearer",
	"access_token": "lkjdjmdniadfodk",
	"expires_in": 3600,
	"scope": "photos",
	"refresh_token": "ADSF34DGA3GD5"
}
```

```http
POST https://authorization-server.com/token? \
	grant_type=refresh_token& \
	refresh_token=REFRESH_TOKEN& \
	client_id=CLIENT_ID
```
