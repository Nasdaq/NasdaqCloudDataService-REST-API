## Financial News - MT Newswires

The MTNewswires Live News Briefs data feed covers news articles from 1,300+ category-coded, US instruments and has over 40,000 unique global symbols.

##### Endpoint

`GET` `https://<base_url>/v1/<source>/<offset>/news/<symbols>/<start-date-and-time>/<categories>`

#### URI Parameters

`<source>` - Data source; acceptable values: `Nasdaq`

`<offset>` - Real-time or 15 minute delayed data; acceptable values: `realtime`

`<symbols>` - Security identifier(s): if more than one, use comma separated list. `*` - for all symbols

`<start-date-and-time>` - date/time (GMT Time). Format: YYYY-MM-DDTHH:MM:SS.ms (e.g. 2026-02-02T10:26:00.000)

`<categories>` - MT News Metadata code. `*` - for all metadata codes

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
[
    {
        "category": [ "AAA","BBB" ],
        “symbol”: “ZVZZT”,
        “language”: “English”,
        "body": "<p>This is a paragraph.</p><p>This is another paragraph.</p>",
        "releaseTime ": "2025/01/27 10:14:59",
        “storyType”: “Extended-Hours”,
        “headline”: “This is the headline.”,
        “articleImage” : “https://.....”,
        “transmissionID” : “ABC123”,
        “revisionID”: “1”,
        “retract”: “FALSE”,
        “copyright”: “Copyright &#169;”
        “isin”: “123”,
        “articleVideo” :”“https://.....”,
        “translatedTransmissionID”: “ABC123.C”,
        “englishTransmissionID” : ”ABC123.E”        
    },
    [...]
]

```

| Field | Name | Type | Description |
|-------|------|------|-------------|
|Category|category|string|Metadata Code|
|Symbol|symbol|string|Stock Symbol associated with the article|
|Language|language|string||
|Body|body|string|The main article text|
|Release Time|releaseTime|string|Date Format: YYYY/MM/DD HH:MM:SS|
|Story Type|storyType|string|Values: "Regular Session" or "Extended Hours"|
|Headline|headline|string|An article only containing a headline has a headline prefixed with “--“|
|Article Image|articleImage|string|Article image link|
|Transmission ID|transmissionID|string|Document's unique identifier|
|Revision ID|revisionID|string|How many times an article has been revised|
|Retraction|retract|string|Represents if an article should be retracted: TRUE or FALSE|
|Copyright|copyright|string|Copyright statement|
|ISIN|isin|string|UK and APAC coverage contains ISIN and street symbols.|
|Article Video|articleVideo|string|Article video link|
|Translation Transmission ID|translationTransmissionID|string||
|English Transmission ID|englishTransmissionID|string||
---

### Example

#### Request

```
curl --location --request GET 'https://example.com/v1//nasdaq/realtime/news/AAPL/2026-02-02T10:26:00.000/*' \
--header "Authorization: Bearer example_token"
```

#### Response

```
{
    "category": [
      "STOK.MN",
      "TNGY.MN",
      "OPUP.MN",
      "REGM.MN",
      "PMKT.MN",
      "EXTND.MN",
      "USUS.MN",
      "NOAM.MN"
    ],
    "symbol": [
      "AAPL"
    ],
    "language": "",
    "body": "\n06:31 AM EST, 02/02/2026 (MT Newswires) -- Apple (AAPL) and other foreign companies in India will be able to provide machines to their contractors in certain regions for five years without any tax risk, according to an official explanation of the country's 2026-2027 budget released Sunday.\nThe proposal to exempt foreign companies from taxes on any income from providing capital goods, equipment, or tooling to a contract manufacturer is being implemented \"to promote manufacturing of electronic goods by a contract manufacturer and provide certainty on taxation of supply of capital equipment by a foreign company to such manufacturer,\" the government said.\nThe tax break is effective April 1 and remains in place until the 2030-2031 tax year, the government said.\nApple did not immediately respond to MT Newswires' request for comment.\n\n",
    "releaseTime": "2026/02/02 06:31:19",
    "storyType": "Extended-Hours",
    "headline": "Apple Granted Indian Tax Break on Funding of Equipment to Contractors",
    "articleImage": "",
    "transmissionID": "A3551113",
    "revisionID": "0",
    "retract": "FALSE",
    "copyright": "http://www.mtnewswires.com\n Copyright © 2026 MT Newswires. All rights reserved. MT Newswires does not provide investment advice. Unauthorized reproduction is strictly prohibited.",
    "isin": [],
    "articleVideo": "",
    "translatedTransmissionID": "",
    "englishTransmissionID": ""
  }
```
