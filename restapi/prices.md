## Prices

The option price and trading details for a given option instrument for current trading day. These are snapshots on the current trading day and prices do not carry over to the next day. 

##### Endpoint

`GET` `https://<base_url>/v1/nasdaq/<offset>/options/prices/<identifier>`

#### URI Parameters

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<identifier>` - Unique identifier of the options contract

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
[
  {
    "identifier": "string",
    "strikePrice": number,
    "optionType": "string",
    "lastPrice": number,
    "lastSize": number,
    "volume": number,
    "askPrice": number,
    "askSize": number,
    "bidPrice": number,
    "bidSize": number,
    "openInterest": number,
    "expiration": "string",
    "tradeTimestamp": "string",
    "askTimestamp": "string",
    "bidTimestamp": "string"
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Identifier|identifier|string |Unique identifier of the options contract: Symbol + Expiration Date + Option Type + Strike Price, using OSI symbology for all US optione; see https://en.wikipedia.org/wiki/Option_symbol. |
|Strike Price|strikePrice|number|The strike price.|
|Option Type|optionType|string|The type of option (P = put or C = call).|
|Last Price|lastPrice|number|The price of the last trade.|
|Volume|volume|number|The day's traded volume of this options contract.|
|Ask Price|askPrice|number|The price of the top ask order.|
|Ask Size|askSize|number|The size of the top ask order.|
|Bid Price|bidPrice|number|The price of the top bid order.|
|Bid Size|bidSize|number|The size of the top bid order.|
|Open Interest|openInterest|number|This options contracts that are still open.|
|Expiration Date|expiration|string|The date on which the option expires. |
|Trade Timestamp|tradeTimestamp|string|The timestamp of the last trade.|
|Ask Timestamp|askTimestamp|string|The timestamp of the top ask order.|
|Bid Timestamp|bidTimestamp|string|The timestamp of the top bid order.|


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/options/prices/ZVZZT 990101P00010000' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "identifier": "ZVZZT 990101P00010000",
    "strikePrice": 10.0,
    "optionType": "P",
    "lastPrice": 0.0,
    "lastSize": 0,
    "volume": 0,
    "askPrice": 0.0,
    "askSize": 0,
    "bidPrice": 0.0,
    "bidSize": 0,
    "openInterest": 0,
    "expiration": "2099-01-01",
    "tradeTimestamp": "",
    "askTimestamp": "2021-12-01T09:35:01.485",
    "bidTimestamp": "2021-12-01T09:35:01.485"
  }
]
```
