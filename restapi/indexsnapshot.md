## Index Snapshot

The latest snapshot of stats, for an index instrument.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/indexes/snapshot/<instrument>`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<instrument>` - Identifier for the index 

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "instrument": "string",
    "summaryType": "string",
    "sodValue": number,
    "high": number,
    "low": number,
    "eodValue": number,
    "netChange": number,
    "timestamp": "string"
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Instrument|instrument|string|The instrument identifier for the NASDAQ or Global Access Program (GAP) Index.|
|Summary Type|string|(see table below)|
|SOD Value|sodValue|number|Start of day value (prior day’s closing price adjustedfor corporate actions).|
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
curl --location --request POST 'https://example.com/v1/nasdaq/realtime/indexes/snapshot/NDX' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "instrument": "NDX",
    "summaryType": "EOD",
    "sodValue": 15092.56790488493,
    "high": 0.0,
    "low": 0.0,
    "eodValue": 0.0,
    "netChange": 0.0,
    "timestamp": "2021-08-23T17:16:02.607"
}
```
