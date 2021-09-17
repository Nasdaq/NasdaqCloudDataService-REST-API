## Exchange Traded Products (ETPs) Snapshot

The latest snapshot of stats, for one or more ETP symbols.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/etps/snapshot/<etpIpvSymbols>`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<etpIpvSymbols>` - ETP identifier(s): if more than one, use comma separated list

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
[
  {
    "etpIpvSymbol": "string",
    "summaryType": "string",
    "sodValue": number,
    "high": number,
    "low": number,
    "eodValue": number,
    "netChange": number,
    "timestamp": "string"
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Instrument|etpIpvSymbol|string|Symbol identifying the ETP's Intraday Portfolio Value (IPV)|
|Summary Type|string|(see table below)|
|SOD Value|sodValue|number|Start of day value (first disseminated tick value).|
|High|high|number|Calculated high value.|
|Low|low|number|Calculated low value|
|EOD Value|eodValue|number|End of day value|
|Net Change|netChange|number|Net chabge.|
|Timestamp|timestamp|string|Trade timestamp, format: YYYY-MM-DDThh:mm:ss.s|

##### Summary Types

| Code | Value |
|-------|------|
|EOD | End of Day Summary|
|SOD | Start of Day Summary|
|PDA | Prior Day Summary Add|
|PDC | Prior Day Summary Correction|
|STL | Settlement Summary|

---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/nasdaq/realtime/etps/snapshot/QXV' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "etpIpvSymbol": "QXV",
    "summaryType": "EOD",
    "sodValue": 367.87,
    "high": 0.0,
    "low": 0.0,
    "eodValue": 0.0,
    "netChange": 0.0,
    "timestamp": "2021-08-23T17:16:05.086"
  }
]
```
