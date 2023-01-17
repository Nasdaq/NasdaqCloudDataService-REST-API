## Bars (Nasdaq, CQT, and OTCBB)

Bars are calculated from 4:00 am to 8:00 pm ET for a given symbol with 10+ years of history.

##### Endpoint

`GET` `https://<base_url>/v2/<source>/<offset>/equities/bars/<symbol>/<precision>/<adjusted>/<date-range>`

#### URI Parameters

`<source>` - Data source; Acceptable values: `Nasdaq`, `CQT`, or `OTCBB`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<symbols>` - Security identifier(s): if more than one, use comma separated list

`<precision>` - Bar precision intervals; acceptable values: `1minute`, `5minute`, `10minute`, `15minute`, `30minute`, `1day`, `1week`, `1month`

`<adjusted>` - Corporate actions adjusted: currently, only `false` supprted (e.g. unadjusted O/H/L/C/V) 

`<date-range>` - Bar date range; acceptable values: `1d` (1 day), `5d` (5 days), `1m` (1 month), `3m` (3 months), `6m` (6 months), `1y` (1 year), `5y` (5 years), `max` (maximum range), `ytd` (year to date)

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
|Date + Timestamp|t|string|Format: YYYY-MM-DDThh:mm:ss.s|
| Open| o| number | The open price is for the beginning of the one-minute period, not the trading session.|
| High| h| number | The high price during the candlestick period is indicated by the top of the shadow or tail above the body. If the open or close was the highest price, then there will be no upper shadow.|
| Low| l| number | The low is indicated by the bottom of the shadow or tail below the body. If the open or close was the lowest price, then there will be no lower shadow.|
| Close| c| number | Last trade of that precision. The close price is for the end of the one-minute period, not the trading session.|
| Volume| v| number | Aggregated shares in that precision. The size of the trades in the time segment selected.|


##### Precision & Date Range Parameter Details

| Range | Description | Finest Precision |
|-------|------|------|
| YTD | Year to date. Time interval would be 1day. | 1 day |
| max | All available data with 10+ years of history. Time interval would be 1month/1week. | 1 week |
| 5y | Five years. Time interval for 5Y would be 1month/1week. | 1 week |
| 1y | One year. Time interval for 1Y would be 1week/1day. | 1 day |
| 6m | Six months. Time interval for 6m would be 1day. | 1 day |
| 3m | Three months. Time interval for 3m would be 1day. | 1 day |
| 1m | One month. Time interval for 1m would be 1day. | 1 day |
| 5d | Five days. Time interval for 5d would be 30minute/15minute/10minute/5minute. | 5 minutes |
| 1d | One day. Time interval would be 1minute/5minute. | 5 seconds |


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v2/cqt/realtime/equities/bars/ZVZZT/5minute/false/5d' \
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
        ],
}
```



