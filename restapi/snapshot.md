## Snapshot

The latest snapshot of stats, according to condition rules, for one or more symbols. 

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/equities/snapshot/<symbols>`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`, `BX`, `PSX`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<symbols>` - Security identifier(s): if more than one, use comma separated list

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
[
  {
    "symbol": "string",
    "timestamp": "string",
    "open": number,
    "high": number,
    "low": number,
    "close": number,
    "lastTrade": number,
    "volume": number,
    "lastSale": number,
    "previousClose": number,
    "netChange": number,
    "percentChange": number
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
| Symbol| symbol| string | |
| Date + Timestamp | timestamp  | string  | Trade timestamp, format: YYYY-MM-DDThh:mm:ss.s |
| Open| open| number | The open price for the symbol in the given time period|
| High| high| number | The highest price for the symbol in the given time period|
| Low| low| number | The lowest price for the symbol in the given time period|
| Close| close| number | The close price for the symbol in the given time period|
| Last Sale| lastSale| number | The latest last sale eligible transaction|
| Volume| volume| number | The trading volume of the symbol in the given time period|
| Last Trade| lastTrade| number | The most recent price of the symbol|
| Previous Day Close | previousClose | number | The adjusted close price for the symbol for the previous day|
| Net Change| netChange| number | The value of the change from the previous day|
| Percent Change     | percentChange | number | The percentage change since the previous day|


---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/nasdaq/realtime/equities/snapshot/ZVZZT' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "symbol": "ZVZZT",
    "timestamp": "2021-07-08T13:30:05.323",
    "open": 10.02,
    "high": 10.03,
    "low": 10.0075,
    "close": 0.0,
    "lastTrade": 10.01,
    "volume": 1097757,
    "lastSale": 10.03,
    "previousClose": 10.02,
    "netChange": 0.009999999999999787,
    "percentChange": 0.09980039920159468
  }
]
```
