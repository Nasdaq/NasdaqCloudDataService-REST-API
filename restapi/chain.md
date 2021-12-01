## Chain

A list of all tradable option instruments for an underlying symbol and a snapshot of price and trading activity on each instrument. Output is sorted in ascending order by Option Type, Expiration Date, Strike Price.

##### Endpoint

`GET` `https://<base_url>/v1/nasdaq/<offset>/options/chain/<symbols>`

#### URI Parameters

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<symbols>` - Security identifier

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
[
  {
    "identifier": "string",
    "symbol": "string",
    "expiration": "string",
    "strikePrice": number,
    "optionType": "string",
    "lastPrice": number,
    "volume": number,
    "askPrice": number,
    "askSize": number,
    "bidPrice": number,
    "bidSize": number,
    "openInterest": number
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Identifier|identifier|string |Unique identifier of the options contract: Symbol + Expiration Date + Option Type + Strike Price, using OSI symbology for all US optione; see https://en.wikipedia.org/wiki/Option_symbol. |
|Symbol|symbol|string|Underlying symbol for option.|
|Expiration Date|expiration|string|The date on which the option expires. |
|Strike Price|strikePrice|number|The strike price.|
|Option Type|optionType|string|The type of option (put or call).|
|Last Price|lastPrice|number|The price of the last trade.|
|Volume|volume|number|The day's traded volume of this options contract.|
|Ask Price|askPrice|number|The price of the top ask order.|
|Ask Size|askSize|number|The size of the top ask order.|
|Bid Price|bidPrice|number|The price of the top bid order.|
|Bid Size|bidSize|number|The size of the top bid order.|
|Open Interest|openInterest|number|This options contracts that are still open.|

---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/nasdaq/realtime/options/chain/ZVZZT' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "identifier": "ZXZZT 990101C00020000",
    "symbol": "ZXZZT",
    "expiration": "2099-01-01",
    "strikePrice": 20.0,
    "optionType": "C",
    "lastPrice": 0.0,
    "volume": 0,
    "askPrice": 0.0,
    "askSize": 0,
    "bidPrice": 0.0,
    "bidSize": 0,
    "openInterest": 0
  }
]
```
