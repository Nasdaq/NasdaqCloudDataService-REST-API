## Authentication

Authenticate to API; returns authentication (access) bearer token.

##### Endpoint

`POST` `https://<base_url>/v1/auth/token`

#### Header

`"Content-Type: application/json"`

#### Request Body

```
{
  "client_id": "<client_id>",
  "client_secret": "<client_secret>"
}
```

#### Response Body

```
{
    "access_token": "string",
    "expires_in": number
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
| Access Token | access_token | string | Bearer Token |
| Expiration | expires_in | number | Token expriation time in seconds |



---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/auth/token' \
--header "Content-Type: application/json" \
--data-raw '{
    "client_id": "example_id",
    "client_secret": "example_secret"
}'
```

#### Response

```
{
    "access_token": "example_token",
    "expires_in": 12345
}
```
