## Symbol Details

Get details for an equities symbol.

##### Endpoint

`GET` `https://<base_url>/v1/reference/symbol/<symbol>`

#### URI Parameters

`<symbol>` - Identifier for the security 

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "symbol": "string",
    "securityName": "string",
    "listingExchange": "string"
    "etf": boolean,
    "ipoFlag": "string"
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Symbol|symbol|string |Identifier of the security used to in various Nasdaq connectivity protocols and NASDAQ market data feeds. Typical identifiers have 1-5 character root symbol and then 1-3 characters for suffixes. Allow up to 14 characters.|
|Security Name|securityName|string |The name of the security including additional information, if applicable. Examples are security type (common stock, preferred stock, etc.) or class (class A or B, etc.). Allow up to 255 characters.|
|Listing Exchange|listingExchange|string |The listing venue or market of a security  (see table below).|
|ETF|etf|boolean|Is this security an Exchange Traded Fund (ETF).|
|IPO Flag|ipoFLag|string|Did the security IPO today (Y|N).|

##### Venues

| Code | Value |
|-------|------|
|Q|The Nasdaq Stock Market|
|N|NYSE|
|A|NYSE American|
|P|NYSE Arca|
|Z|BATS|
|V|Investors’ Exchange LLC|


---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/reference/symbol/ZXZZT' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "symbol": "ZXZZT",
    "securityName": "NASDAQ TEST STOCK",
    "etf": false,
    "listingExchange": "Q",
    "ipoFlag": "N",
}
```
