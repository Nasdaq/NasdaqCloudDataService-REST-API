## Index Value

Get intraday value for one or more index instruments.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/indexes/value/<instruments>`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`, `delayed`

`<instruments>` - Index identifier(s): if more than one, use comma separated list

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
[
  {
    "instrument": "string",
    "tickValue": number,
    "timestamp": "string"
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Instrument|instrument|string|The instrument identifier for the NASDAQ or Global Access Program (GAP) Index.|
|Tick Value|tickValue|number|The current calculated tick value for instrument.|
|Timestamp|timestamp|string|Trade timestamp, format: YYYY-MM-DDThh:mm:ss.s|


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/nasdaq/realtime/indexes/value/NDX' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "instrument": "NDX",
    "tickValue": 15312.81588491499,
    "timestamp": "2021-08-23T17:10:35.125"
  }
]
```
