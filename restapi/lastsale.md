## Last Sale

The latest last sale eligible transaction, according to condition rules, for one or more symbols.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/equities/lastsale/<symbols>`

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
    "price": number,
    "size": number,
    "conditions": "string",
    "exchange": "string",
    "securityClass": "string",
    "changeIndicator": number
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
| Date + Timestamp | timestamp  | string  | Trade timestamp, format: YYYY-MM-DDThh:mm:ss.s |
| Symbol| symbol| string  ||
| Price| price| number  ||
| Size| size| number ||
| Exchange| exchange| string  | Exchange where trade took place (see table below)|
| Conditions| conditions | string  | SAle condition modifier consists of four levels  (see table below)|
| Security Class| securityClass| string  |Indicates Listing Venue (see table below)|
| Change Indicator| changeIndicator| number  | Change from previous sale: downtick (-1); flat (0); uptick (+1); |

##### Conditions

Level 1 - Settlement type information
| Code | Value |
|-------|------|
|@|Regular Settlement|
|C|Cash Settlement|
|N|Next Day Settlement|
|R|Seller Settlement|

Level 2 - [SEC Regulation NMS](http://www.nasdaqtrader.com/Trader.aspx?id=RegNMS) trade through exemption codes
| Code | Value |
|-------|------|
|F|Intermarket Sweep|
|O|Opening Print|
|4|Derivative Priced|
|5|Re-Opening Print|
|6|Closing Print
|7|Qualified Contingent Trade (QCT)
|< space >|Not applicable|

Level 3 - Extended hours or sold codes
| Code | Value |
|-------|------|
|T|Extended Hours Trade|
|U|Extended Hours Trade –Reported Late or Out of Sequence|
|L|Sold Last –Reported Late But In Sequence|
|Z|Sold –Out of Sequence|
|< space >|Not applicable|

Level 4 - Special sale condition codes (field is case sensitive)
| Code | Value |
|-------|------|
|A|Acquisition|
|B|Bunched|
|D|Distribution|
|H|Price Variation Transaction|
|M|Nasdaq Official Close Price (NOCP)|
|P|Prior Reference Price|
|Q|Nasdaq Official Opening Price (NOOP)|
|S|Split Trade|
|V|Contingent Trade|
|W|Average Price Trade|
|X|Cross Trade|
|o|Odd Lot Xxecution|
|x|Odd Lot Cross Execution|
|< space >|Not applicable|

##### Exchanges

| Code | Value |
|-------|------|
|Q|The Nasdaq Stock Market|
|L|Nasdaq/FINRA Trade Reporting Facility (TRF) Cartaret|
|2|Nasdaq/FINRA Trade Reporting Facility (TRF) Chicago|
|B|Nasdaq BX (BX)|
|X|Nasdaq PSX (PSX)|

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
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/equities/lastsale/ZVZZT' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "symbol": "ZVZZT",
    "timestamp": "2021-07-09T09:17:01.383",
    "price": 10.15,
    "size": 9,
    "conditions": "@ To",
    "exchange": "Q",
    "securityClass": "Q",
    "changeIndicator": 0
  }
]
```
