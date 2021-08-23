## Index Participants

List the component securities for an index.

##### Endpoint

`GET` `https://<base_url>/v1/reference/indexparticipants/<instrument>`

#### URI Parameters

`<instrument>` - Identifier for the index 

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "instrument": "COMP",
    "participants": [
        {
            "issueSymbol": "string",
            "issueMIC": "string",
            "issueName": "string"
        },
        [...]
    ],
    "timeStamp": "string"
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Instrument|instrument|string|The instrument identifier for the NASDAQ OMX or Global Access Program (GAP) Index.|
|Issue Symbol|issueSymbol|string|A list of the security trading symbols for the component securities, as assigned by the Issue MIC.|
|Issue MIC|issueMIC|string|The ISO 10383 Market Identification Code (MIC) of the component security’s primary.|
|Instrument Name|instrumentName|string|The Instrument Name or Index Name from NASDAQ or GAP.|


---


### Example

#### Request

```
curl --location --request POST 'https://example.com/v1/indexparticipants/XXZZT' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "instrument": "COMP",
    "participants": [
        {
            "issueSymbol": "ZZXXT",
            "issueMIC": "ZZZZZ",
            "issueName": "Test instrument 1"
        },
        {
            "issueSymbol": "XXZZT",
            "issueMIC": "YYYYY",
            "issueName": "Test Instrument 2"
        }
    ],
    "timeStamp": "2021-08-23T01:25:21.941"
}
```
