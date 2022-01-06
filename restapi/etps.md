## All Exchange Traded Products (ETPs)

List all supported ETPs symbols.

##### Endpoint

`GET` `https://<base_url>/v1/reference/etps`

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
    "name": "string",
    [...]
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|ETP Trading Symbol|symbol|string|Denotes the ETP instrument trading symbol for the NASDAQ OMX or Global Access Program (GAP) as assigned by the listing market.|
|ETP Name|name|string|ETP instrument Name|


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/reference/etps' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
    {
        "symbol": "QQQ",
        "name": "PowerShares QQQ Trust, Ser 1"
    },
    {
        "symbol": "QQQA",
        "name": "ProShares Nasdaq-100 Dorsey Wright Momentum ETF"
    }
]
```
