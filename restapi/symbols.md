## All Symbols

List all supported equities symbols.

##### Endpoint

`GET` `https://<base_url>/v1/reference/symbols`

#### URI Parameters

none

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "symbol": "string",
    [...]
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Symbol|symbol|string|Identifier of the security used to in various Nasdaq connectivity protocols and Nasdaq market data feeds. Typical identifiers have 1-5 character root symbol and then 1-3 characters for suffixes. Allow up to 14 characters.|
|Security Name|securityName|string|The name of the security including additional information, if applicable. Examples are security type (common stock, preferred stock, etc.) or class (class A or B, etc.). Allow up to 255 characters.|


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/reference/symbols' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "ZVZZT": "NASDAQ TEST STOCK",
    "ZWZZT": "NASDAQ TEST STOCK",
    "ZXZZT": "NASDAQ TEST STOCK"
}
```
