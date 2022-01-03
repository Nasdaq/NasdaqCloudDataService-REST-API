## Index Details

Get details for an index instrument.

##### Endpoint

`GET` `https://<base_url>/v1/reference/index/<instrument>`

#### URI Parameters

`<instrument>` - Identifier for the index 

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "instrument": "string",
    "instrumentName": "string",
    "fpType": "string",
    "assetType": "string",
    "currency": "string",
    "calculationMethod": "string",
    "state": "string",
    "schedule": "string",
    "frequency": string",
    "baseDate": number
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Instrument|instrument|string|The instrument identifier for the NASDAQ or Global Access Program (GAP) Index.|
|Instrument Name|instrumentName|string|The Instrument Name or Index Name from NASDAQ or GAP.|
|Financial Product Type|fpType|CC|(see table below)|
|Asset Type|assetType|string|The NASDAQ or GAP primary asset class for the Instrument ID.|
|Currency|currency|string|The ISO 4217 Currency Code for the Instrument ID.|
|Index Calculation Method|calculationMethod|string|Denotes the NASDAQ OMX or GAP Index Calculation Method code associated with the Instrument ID in the directory message. |
|State|state|string|Denotes the current NASDAQ OMX or GAP state associated with the Instrument ID in the directory message. |
|Schedule|schedule|string|Denotes the NASDAQ OMX or GAP dissemination schedule associated with the Instrument ID in the directory message. |
|Frequency|frequency|string|Denotes the NASDAQ OMX or GAP frequency code associated with the Instrument ID in the directory message.|
|Base Date|baseDate|number|Inception date of the index. Format: YYYYYMMDD|


##### Financial Product Types

| Code | Value |
|-------|------|
|<blank> Not Specified|
|I| Index|
|E| Exchange Traded Fund (ETF)|
|N| Exchange Traded Note (ETN)|
|F| Exchange Traded Managed Fund (ETMF)|
|S| Settlement|
|P| Spot|
|L| Subordinated product|
|W| World Currency|
|A| Alpha Index|

---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/reference/index/NDX' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "instrument": "NDX",
    "instrumentName": "NASDAQ-100",
    "fpType": "I",
    "assetType": "EQ",
    "currency": "USD",
    "calculationMethod": "PR ",
    "state": "A",
    "schedule": "AME",
    "frequency": "1S",
    "baseDate": 19940101
}
```
