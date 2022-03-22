## Trends

Top 20 gaining & declining equities. For market hours only.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/equities/trends`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`, `BX`, `PSX`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

optional component
gainers|decliners|mostactivebyvolume|mostactivebydollarvolume

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
      "symbol": "string",
      "cummulativeVolume": number,
      "dollarAmountTraded": number
    },
    [...]
  ],
  "decliners": [
    {
      "lastTrade": number,
      "lastSale": number,
      "netChange": number,
      "percentChange": number,
      "symbol": "string",
      "cummulativeVolume": number,
      "dollarAmountTraded": number
    },
    [...]
  ],
  "mostActiveByVolume": [
    {
      "lastTrade": number,
      "lastSale": number,
      "netChange": number,
      "percentChange": number,
      "symbol": "string",
      "cummulativeVolume": number,
      "dollarAmountTraded": number
    },
    [...]
  ],
  "mostActiveByDollarAmount": [
    {
      "lastTrade": number,
      "lastSale": number,
      "netChange": number,
      "percentChange": number,
      "symbol": "string",
      "cummulativeVolume": number,
      "dollarAmountTraded": number
    },
    [...]
  ]
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Date + Timestamp|timestamp|string|Format: YYYY-MM-DDThh:mm:ss.s|
|gainers         |               ||
|Symbol          |symbol         |string||
|Last Sale       |lastSale       |number|The latest last sale eligible transaction|
|Last Trade      |lastTrade      |number |If outside of market hours, these prices could be different|
|Net Change      |netChange      |number|The value of the change from the previous day|
|Percent Change  |percentChange  |number|The percentage change since the previous day|
|Cummulative Volume |cummulativeVolume      |number|The total number of shared traded today|
|Dollar Amount Traded  |dollarAmountTraded  |number|The dollar amount of shares traded today|
decliners       |               ||
|Symbol          |symbol         |string||
|Last Sale       |lastSale       |number|The latest last sale eligible transaction|
|Last Trade      |lastTrade      |number |If outside of market hours, these prices could be different|
|Net Change      |netChange      |number|The value of the change from the previous day|
|Percent Change  |percentChange  |number|The value of the change from the previous day|
|Cummulative Volume |cummulativeVolume      |number|The total number of shared traded today|
|Dollar Amount Traded  |dollarAmountTraded  |number|The dollar amount of shares traded today|
|mostActiveByVolume         |               ||
|Symbol          |symbol         |string||
|Last Sale       |lastSale       |number|The latest last sale eligible transaction|
|Last Trade      |lastTrade      |number |If outside of market hours, these prices could be different|
|Net Change      |netChange      |number|The value of the change from the previous day|
|Percent Change  |percentChange  |number|The percentage change since the previous day|
|Cummulative Volume |cummulativeVolume      |number|The total number of shared traded today|
|Dollar Amount Traded  |dollarAmountTraded  |number|The dollar amount of shares traded today|
|mostActiveByDollarAmount       |               ||
|Symbol          |symbol         |string||
|Last Sale       |lastSale       |number|The latest last sale eligible transaction|
|Last Trade      |lastTrade      |number |If outside of market hours, these prices could be different|
|Net Change      |netChange      |number|The value of the change from the previous day|
|Percent Change  |percentChange  |number|The value of the change from the previous day|
|Cummulative Volume |cummulativeVolume      |number|The total number of shared traded today|
|Dollar Amount Traded  |dollarAmountTraded  |number|The dollar amount of shares traded today|

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
    "timestamp": "2022-03-22T10:09:05.175",
    "gainers": [
        {
            "lastTrade": 5.915,
            "lastSale": 5.915,
            "netChange": 3.915,
            "percentChange": 195.75,
            "symbol": "LLL",
            "cummulativeVolume": 19801469,
            "dollarAmountTraded": 5.813118579520002E7
        },
        {
            "lastTrade": 19.14,
            "lastSale": 19.14,
            "netChange": 9.03,
            "percentChange": 89.3175,
            "symbol": "FRGE",
            "cummulativeVolume": 489224,
            "dollarAmountTraded": 4767073.346800001
        },
        {
            "lastTrade": 3.12,
            "lastSale": 3.12,
            "netChange": 1.45,
            "percentChange": 86.8263,
            "symbol": "DPRO",
            "cummulativeVolume": 95190525,
            "dollarAmountTraded": 1.5619760153419948E8
        },
        [...]
    ],
    "decliners": [
        {
            "lastTrade": 0.2055,
            "lastSale": 0.2055,
            "netChange": -0.2245,
            "percentChange": -52.2093,
            "symbol": "GIACW",
            "cummulativeVolume": 2200,
            "dollarAmountTraded": 445.49000000000007
        },
        {
            "lastTrade": 0.65,
            "lastSale": 0.65,
            "netChange": -0.5,
            "percentChange": -43.4783,
            "symbol": "NRSNW",
            "cummulativeVolume": 238955,
            "dollarAmountTraded": 88407.44219999998
        },
        {
            "lastTrade": 0.3435,
            "lastSale": 0.3435,
            "netChange": -0.2508,
            "percentChange": -42.2009,
            "symbol": "STAB",
            "cummulativeVolume": 6046556,
            "dollarAmountTraded": 1239472.0120000027
        },
        [...]
    ],
    "mostActiveByVolume": [
        {
            "lastTrade": 3.12,
            "lastSale": 3.12,
            "netChange": 1.45,
            "percentChange": 86.8263,
            "symbol": "DPRO",
            "cummulativeVolume": 95190525,
            "dollarAmountTraded": 1.5619760153419948E8
        },
        {
            "lastTrade": 2.9998,
            "lastSale": 2.9998,
            "netChange": -0.2102,
            "percentChange": -6.5483,
            "symbol": "MULN",
            "cummulativeVolume": 73708111,
            "dollarAmountTraded": 1.199778064516994E8
        },
        {
            "lastTrade": 1.14,
            "lastSale": 1.14,
            "netChange": 0.2099,
            "percentChange": 22.5675,
            "symbol": "SMFL",
            "cummulativeVolume": 36757358,
            "dollarAmountTraded": 2.2012523723100122E7
        },
        [...]
    ],
    "mostActiveByDollarAmount": [
        {
            "lastTrade": 933.93,
            "lastSale": 934.07,
            "netChange": 12.91,
            "percentChange": 1.4015,
            "symbol": "TSLA",
            "cummulativeVolume": 5286750,
            "dollarAmountTraded": 2.835933798284003E9
        },
        {
            "lastTrade": 447.94,
            "lastSale": 447.93,
            "netChange": 3.54,
            "percentChange": 0.7966,
            "symbol": "SPY",
            "cummulativeVolume": 10232366,
            "dollarAmountTraded": 2.0673594967130787E9
        },
        {
            "lastTrade": 353.8999,
            "lastSale": 353.8999,
            "netChange": 3.8199,
            "percentChange": 1.0912,
            "symbol": "QQQ",
            "cummulativeVolume": 11782690,
            "dollarAmountTraded": 2.015403218506805E9
        },
        [...]
    ]
}
```

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/equities/trends/gainers' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "timestamp": "2022-03-22T10:09:05.175",
    "gainers": [
        {
            "lastTrade": 5.915,
            "lastSale": 5.915,
            "netChange": 3.915,
            "percentChange": 195.75,
            "symbol": "LLL",
            "cummulativeVolume": 19801469,
            "dollarAmountTraded": 5.813118579520002E7
        },
        {
            "lastTrade": 19.14,
            "lastSale": 19.14,
            "netChange": 9.03,
            "percentChange": 89.3175,
            "symbol": "FRGE",
            "cummulativeVolume": 489224,
            "dollarAmountTraded": 4767073.346800001
        },
        {
            "lastTrade": 3.12,
            "lastSale": 3.12,
            "netChange": 1.45,
            "percentChange": 86.8263,
            "symbol": "DPRO",
            "cummulativeVolume": 95190525,
            "dollarAmountTraded": 1.5619760153419948E8
        },
        [...]
    ]
}
```

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/equities/trends/decliners' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "timestamp": "2022-03-22T10:09:05.175",
    "decliners": [
        {
            "lastTrade": 0.2055,
            "lastSale": 0.2055,
            "netChange": -0.2245,
            "percentChange": -52.2093,
            "symbol": "GIACW",
            "cummulativeVolume": 2200,
            "dollarAmountTraded": 445.49000000000007
        },
        {
            "lastTrade": 0.65,
            "lastSale": 0.65,
            "netChange": -0.5,
            "percentChange": -43.4783,
            "symbol": "NRSNW",
            "cummulativeVolume": 238955,
            "dollarAmountTraded": 88407.44219999998
        },
        {
            "lastTrade": 0.3435,
            "lastSale": 0.3435,
            "netChange": -0.2508,
            "percentChange": -42.2009,
            "symbol": "STAB",
            "cummulativeVolume": 6046556,
            "dollarAmountTraded": 1239472.0120000027
        },
        [...]
    ]
}
```

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/equities/trends/mostactivebyvolume' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "timestamp": "2022-03-22T10:09:05.175",
    "mostActiveByVolume": [
        {
            "lastTrade": 3.12,
            "lastSale": 3.12,
            "netChange": 1.45,
            "percentChange": 86.8263,
            "symbol": "DPRO",
            "cummulativeVolume": 95190525,
            "dollarAmountTraded": 1.5619760153419948E8
        },
        {
            "lastTrade": 2.9998,
            "lastSale": 2.9998,
            "netChange": -0.2102,
            "percentChange": -6.5483,
            "symbol": "MULN",
            "cummulativeVolume": 73708111,
            "dollarAmountTraded": 1.199778064516994E8
        },
        {
            "lastTrade": 1.14,
            "lastSale": 1.14,
            "netChange": 0.2099,
            "percentChange": 22.5675,
            "symbol": "SMFL",
            "cummulativeVolume": 36757358,
            "dollarAmountTraded": 2.2012523723100122E7
        },
        [...]
    ]
}
```

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/equities/trends/mostactivebydollarvolume' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "timestamp": "2022-03-22T10:09:05.175",
    "mostActiveByDollarAmount": [
        {
            "lastTrade": 933.93,
            "lastSale": 934.07,
            "netChange": 12.91,
            "percentChange": 1.4015,
            "symbol": "TSLA",
            "cummulativeVolume": 5286750,
            "dollarAmountTraded": 2.835933798284003E9
        },
        {
            "lastTrade": 447.94,
            "lastSale": 447.93,
            "netChange": 3.54,
            "percentChange": 0.7966,
            "symbol": "SPY",
            "cummulativeVolume": 10232366,
            "dollarAmountTraded": 2.0673594967130787E9
        },
        {
            "lastTrade": 353.8999,
            "lastSale": 353.8999,
            "netChange": 3.8199,
            "percentChange": 1.0912,
            "symbol": "QQQ",
            "cummulativeVolume": 11782690,
            "dollarAmountTraded": 2.015403218506805E9
        },
        [...]
    ]
}
```
