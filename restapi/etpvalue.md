## Exchange Traded Product (ETP) Value

Get intraday value for one or more ETP symbols.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/etps/value/<etpIpvSymbols>`

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
    "ipvValue": number,
    "timestamp": "string"
  }
]
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Instrument|etpIpvSymbol|string|Symbol identifying the ETP's Intraday Portfolio Value (IPV)|
|IPV Value|ipvValue|number|The current calculated value for the IPV symbol.|
|Timestamp|timestamp|string|Trade timestamp, format: YYYY-MM-DDThh:mm:ss.s|


---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/nasdaq/realtime/etps/value/QXV' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
  {
    "etpIpvSymbol": "QXV",
    "ipvValue": 373.23,
    "timeStamp": "2021-08-23T17:15:59.212"
  }
]
```
