## Exchange Traded Products (ETPs) Details

Get details for an Exchange Traded Products (ETPs) symbol.

##### Endpoint

`GET` `https://<base_url>/v1/reference/etp/<symbol>`

#### URI Parameters

`<symbol>` - Symbol for the ETP 

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "symbol": "string",
    "name": "string",
    "fpType": "string",
    "etpIpvSymbol": "string",
    "state": "string",
    "navSymbol": "string",
    "ecuSymbol": "string",
    "totalCashSymbol": "string",
    "ecsSymbol": "string",
    "tsoSymbol": "string",
    "effectiveDate": 20210823
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|ETP Trading Symbol|symbol|string|Denotes the ETP instrument trading symbol for the NASDAQ OMX or Global Access Program (GAP) as assigned by the listing market.|
|ETP Name|name|string|ETP instrument Name|
|Financial Product Type|fpType|CC|(see table below)|
|ETP IPV Symbol|etpIpvSymbol|string|Symbol identifying the Intraday Portfolio Value (IPV) (i.e.: ABCD.IV; ABCDI)|
|State|BB|state|Denotes the current NASDAQ OMX or GAP state associated with the ETP IPV symbol in the directory message. |
|NAV Symbol|navSymbol|string|Symbol identifying the Net Asset Value per Creation Unit (ie: ABCD.NV; ABCDN)|
|Estimated Cash Per CU Symbol|ecuSymbol|string|Symbol identifying the Estimated Cash Per Creation Unit (ie: ABCD.EU; ABCDM)|
|Total Cash Per CU Symbol|totalCashSymbol|string|Symbol identifying the Total Cash Amount Per Creation Unit (ie: ABCD.TC; ABCDT)|
|Estimated Cash Per Share Symbol|ecsSymbol|string|Symbol identifying the Estimated Cash Per Share -Net Accrued Dividend. (ie: ABCD.DV;ABCDD)|
|TSO Symbol|tsoSymbol|string|Symbol identifying the Total Shares Outstanding (ie: ABCD.SO; ABCDS)|
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
curl --location --request POST 'https://example.com/v1/reference/etp/QQQ' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "symbol": "QQQ",
    "name": "PowerShares QQQ Trust, Ser 1",
    "fpType": "E",
    "etpIpvSymbol": "QXV",
    "state": "A",
    "navSymbol": "QQQ.NV",
    "ecuSymbol": "QQQ.EU",
    "totalCashSymbol": "QQQ.TC",
    "ecsSymbol": "QQQ.DV",
    "tsoSymbol": "QQQ.SO",
    "effectiveDate": 20210823
}
```
