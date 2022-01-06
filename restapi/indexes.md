## All Indexes

List all supported indexes instruments.

##### Endpoint

`GET` `https://<base_url>/v1/reference/indexes`

#### URI Parameters

none

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
{
    "instrument": "name",
    "instrumentName": "name",
}
```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Instrument|instrument|string|The instrument identifier for the NASDAQ OMX or Global Access Program (GAP) Index.|
|Instrument Name|instrumentName|string|The Instrument Name or Index Name from NASDAQ or GAP.|


---


### Example

#### Request

```
curl --location --request GET 'https://example.com/v1/reference/indexes' \
--header "Authorization: Bearer example_token"
```

#### Response

```
[
    {
        "instrument": "COMP",
        "instrumentName": "NASDAQ Composite"
    },
    {
        "instrument": "NDX",
        "instrumentName": "NASDAQ-100"
    }
]
```
