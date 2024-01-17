## Last Quote

The latest last eligible quote, according to condition rules, for one or more symbols.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/equities/lastquote/<symbols>`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`, `BX`, `PSX`, `CQT`

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
    "bidPrice": number,
    "bidSize": number,
    "bidVenue": "string",
    "askPrice": number,
    "askSize": number,
    "askVenue": "string"
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
| Date + Timestamp | timestamp  | string  | Last update on this quote (one side or two sided quotes), format: YYYY-MM-DDThh:mm:ss.s |
| Symbol| symbol     | string  ||
| Bid Price| bidPrice   | number  |The highest price a buyer will pay to buy a specified number of shares of a stock at any given time|
| Bid Size| bidSize    | number |This represents the number of round lot orders at the given bid price|
| Bid Venue| bidVenue   | string  | Exchange where quote took place (see table below)|
| Ask Price| askPrice   | number  |The lowest price at which a seller will sell the stock|
| Ask Size| askSize    | number |This represents the number of round lot orders at the given ask price|
| Ask Venue| askVenue   | string  | Exchange where quote took place (see table below)|

##### Exchanges

| Source | Code | Value |
|-------|-------|------|
|`Nasdaq`, `BX`, `PSX`, `CQT`|Q |The Nasdaq Stock Market |
|`CQT`|N |New York Stock Exchange, LLC |
|`CQT`|B |Nasdaq BX, Inc.|
|`CQT`|E |Market Independent |
|`CQT`|D |FINRA Alternative Display Facility |
|`CQT`|Z |Cboe BZX Exchange, Inc. |
|`CQT`|T |The NASDAQ Stock Market, LLC |
|`CQT`|I |International Securities Exchange 
|`CQT`|U |Members Exchange |
|`CQT`|W |Cboe Stock Exchange |
|`CQT`|u |Other OTC Markets |
|`CQT`|J |Cboe EDGA Exchange, Inc. |
|`CQT`|M |Chicago Stock Exchange |
|`CQT`|Y |Cboe BYX Exchange, Inc. |
|`CQT`|C |NYSE National, Inc. |
|`CQT`|X |Nasdaq PSX (PSX) |
|`CQT`|A |NYSE American |
|`CQT`|K |Cboe EDGX Exchange, Inc. |
|`CQT`|P |NYSE Arca, Inc. |
|`CQT`|L |Long-term Stock Exchange |
|`CQT`|H |MIAX Exchange |

---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/equities/lastquote/ZVZZT' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "symbol": "ZVZZT",
    "timestamp": "2021-07-09T09:04:32.517",
    "bidPrice": 9.99,
    "bidSize": 140,
    "bidVenue": "Q",
    "askPrice": 10.15,
    "askSize": 1081,
    "askVenue": "Q"
  }
]
```
