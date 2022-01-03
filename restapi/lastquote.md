## Last Quote

The latest last eligible quote, according to condition rules, for one or more symbols.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/equities/lastquote/<symbols>`

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
