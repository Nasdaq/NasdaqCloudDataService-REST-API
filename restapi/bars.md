## Bars (BX and PSX)

Bars are calculated from 4:00 am to 8:00 pm ET for a given symbol(up to 5 days of history). Eligibility rules are applied only during market hours(Excluded pre-market and post-market).

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/equities/bars/<symbol>/<precision>/<start-date-and-time>/<end-date-and-time>`

#### URI Parameters

`<source>` - Data source; acceptable values: `BX` and `PSX`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<precision>` - Bar precision intervals; acceptable values: `1minute`, `5minute`

`<start-date-and-time>` & `<end-date-and-time>` - Bars date/time ranges (Eastern Time)

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
 { 
        "ZVZZT": [ 
            { 
                "t": "2021-10-29T09:30:00.000", 
                "o": 206.64, 
                "h": 206.64, 
                "l": 0.0, 
                "c": 206.57, 
                "v": 7965 
            }, 
            [...] 
        ], 
        "ZVVZT": [ 
            { 
                "t": "2021-10-29T09:30:00.000", 
                "o": 206.64, 
                "h": 206.64, 
                "l": 0.0, 
                "c": 206.57, 
                "v": 7965 
             }, 
             [...] 
          ], 
          [...] 
  } 
```


| Field | Name | Type | Description |
|-------|------|------|-------------|
|Date + Timestamp|timestamp|string|Format: YYYY-MM-DDThh:mm:ss.s|
| Open| o| number | The open price is for the beginning of the one-minute period, not the trading session.|
| High| h| number | The high price during the candlestick period is indicated by the top of the shadow or tail above the body. If the open or close was the highest price, then there will be no upper shadow.|
| Low| l| number | The low is indicated by the bottom of the shadow or tail below the body. If the open or close was the lowest price, then there will be no lower shadow.|
| Close| c| number | Last trade of that precision. The close price is for the end of the one-minute period, not the trading session.|
| Volume| v| number | Aggregated shares in that precision. The size of the trades in the time segment selected.|


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/bx/realtime/equities/bars/ZVZZT/1minute/2021-10-29T09:30/2021-20-29T10:00' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{ 
        "ZVZZT": [ 
            { 
                "t": "2021-10-29T09:30:00.000", 
                "o": 206.64, 
                "h": 206.64, 
                "l": 0.0, 
                "c": 206.57, 
                "v": 7965 
            }, 
            [...] 
        ]
}
```



