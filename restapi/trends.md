## Trends

Top 5 gaining & declining equities. For market hours only.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/equities/trends`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`, `BX`, `PSX`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
  "timestamp": "string",
  "gainers": [
    {
      "lastTrade": number,
      "lastSale": number,
      "netChange": number,
      "percentChange": number,
      "symbol": "string"
    },
    [...]
  ],
  "decliners": [
    {
      "lastTrade": number,
      "lastSale": number,
      "netChange": number,
      "percentChange": number,
      "symbol": "string"
    },
    [...]
  ]
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Date + Timestamp|timestamp|string|Format: YYYY-MM-DDThh:mm:ss.s|
|Gainers         |               ||
|Symbol          |symbol         |string||
|Last Sale       |lastSale       |number|The latest last sale eligible transaction|
|Last Trade      |lastTrade      |number |If outside of market hours, these prices could be different|
|Net Change      |netChange      |number|The value of the change from the previous day|
|Percent Change  |percentChange  |number|The percentage change since the previous day|
|Decliners       |               ||
|Symbol          |symbol         |string||
|Last Sale       |lastSale       |number|The latest last sale eligible transaction|
|Last Trade      |lastTrade      |number |If outside of market hours, these prices could be different|
|Net Change      |netChange      |number|The value of the change from the previous day|
|Percent Change  |percentChange  |number|The value of the change from the previous day|


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/equities/trends' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
  "timestamp": "2021-07-07T16:00:58.751",
  "gainers": [
    {
      "lastTrade": 67.51,
      "lastSale": 67.57,
      "netChange": 40.37,
      "percentChange": 148.4191,
      "symbol": "AABBCC"
    },
    {
      "lastTrade": 2.72,
      "lastSale": 2.72,
      "netChange": 1.09,
      "percentChange": 66.8712,
      "symbol": "BBCCDD"
    },
    {
      "lastTrade": 1.35,
      "lastSale": 1.35,
      "netChange": 0.45,
      "percentChange": 50,
      "symbol": "CCDDEE+"
    },
    {
      "lastTrade": 43.71,
      "lastSale": 43.71,
      "netChange": 14.51,
      "percentChange": 49.6918,
      "symbol": "EEFFGG"
    },
    {
      "lastTrade": 3.34,
      "lastSale": 3.34,
      "netChange": 1.08,
      "percentChange": 47.7876,
      "symbol": "GGHHII"
    }
  ],
  "decliners": [
    {
      "lastTrade": 0.9701,
      "lastSale": 0.9701,
      "netChange": -1.8799,
      "percentChange": -65.9614,
      "symbol": "QQRRSS"
    },
    {
      "lastTrade": 8.6,
      "lastSale": 8.55,
      "netChange": -3.68,
      "percentChange": -30.0899,
      "symbol": "SSTTUU"
    },
    {
      "lastTrade": 5.02,
      "lastSale": 5.05,
      "netChange": -2,
      "percentChange": -28.3688,
      "symbol": "UUVVWW"
    },
    {
      "lastTrade": 0.2921,
      "lastSale": 0.2921,
      "netChange": -0.0879,
      "percentChange": -23.1316,
      "symbol": "WWXXYY"
    },
    {
      "lastTrade": 2.26,
      "lastSale": 2.26,
      "netChange": -0.62,
      "percentChange": -21.5278,
      "symbol": "YYZZAA"
    }
  ]
}
```
