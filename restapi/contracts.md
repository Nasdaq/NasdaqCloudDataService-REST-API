## All Option Contracts

List all option identifiers available for an underlying symbol.

##### Endpoint

`GET` `https://<base_url>/v1/reference/contracts/<symbol>`

#### URI Parameters

`<symbol>` - Identifier for the security 

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "identifier": "ZXZZT 990101C00025000",
    "symbol": "ZXZZT",
    "expiration": "2099-01-01",
    "strikePrice": 25.0,
    "optionType": "C"
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Identifier|identifier|string |Unique identifier of the options contract: Symbol + Expiration Date + Option Type + Strike Price, using OSI symbology for all US optione; see https://en.wikipedia.org/wiki/Option_symbol. |
|Symbol|symbol|string|Underlying symbol for option.|
|Expiration Date|expiration|string|The date on which the option expires. |
|Strike Price|strikePrice|number|The strike price.|
|Option Type|optionType|string|The type of option (put or call).|


---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/reference/contracts/ZXZZT' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "identifier": "ZXZZT 990101C00025000",
    "symbol": "ZXZZT",
    "expiration": "2099-01-01",
    "strikePrice": 25.0,
    "optionType": "C"
}
```
