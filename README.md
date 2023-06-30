# Nasdaq Data Link - REST API for real-time or delayed data

Nasdaq Data Link provides a modern and efficient method of delivery for realtime exchange data and other financial information. Data is made available through a suite of APIs, allowing for effortless integration of data from disparate sources, and a dramatic reduction in time to market for customer-designed applications. The API is highly scalable, and robust enough to support the delivery of real-time exchange data. Read our latest case study: <a href="https://www.nasdaq.com/docs/2022/10/09/2107-Q22_NDL_Unhedged-Case-Study.pdf">Nasdaq Data Link Provides Real-Time Data with Efficiency and Scale to Fintech Newcomer Unhedged</a> 

## Table of Contents

- [Products Currently Available](#products-currently-available)
- [Getting Started](#getting-started)
- [Authentication](#authentication)
- [API Resources](#api-resources)
- [Versioning](#versioning)
- [HTTP Response Codes](#http-response-codes)
- [Tutorial](#tutorial)
- [License](#license)

## Products Currently Available

### Equities

#### The Nasdaq Stock Market

- [Nasdaq Basic](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/NasdaqBasic-Cloud.pdf)
- [Nasdaq Last Sale+](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/NLSPlus-cloud.pdf) 

#### Nasdaq BX

- [BX BBO](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/BX_BBO_Cloud.pdf)
- [BX Last Sale](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/BLS_Cloud.pdf)

#### Nasdaq PSX

- [PSX BBO](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/PSX_BBO_Cloud.pdf)
- [PSX Last Sale](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/PLS_Cloud.pdf)

#### All U.S. Equity Markets
- [Nasdaq Consolidated Quotes and Trades](https://github.com/Nasdaq/CloudDataService/raw/master/specs/CQT-cloud.pdf)

### Indexes & Exchange Traded Products (ETPs)

- [Global Index Data Service](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/GIDS_Cloud.pdf)

### Options

- [Nasdaq Smart Options](http://nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/NCDSSmartOptions.pdf)
- [Nasdaq Options Greeks and Implied Volatility](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/GreeksandVols_Specification.pdf)

## Getting Started

The customer service team will provide you with the API URL (`<base_url>`), username (`client_id`), and password (`client_secret`). Substitute for these placeholders with actual values in your code.

## Authentication

Access to the API is granted by providing your client_id and client_secret using OAuth 2.0 authentication. 

## API Resources

### General

- [`POST` Authenticate](restapi/authenticate.md)

### Equities

- [`GET` Last Sale](restapi/lastsale.md)
- [`GET` Last Trade](restapi/lasttrade.md)
- [`GET` Last Quote](restapi/lastquote.md)
- [`GET` Snapshot](restapi/snapshot.md)
- [`GET` Trends](restapi/trends.md)
- [`GET` Bars (BX and PSX)](restapi/bars.md)
- [`GET` Bars (Nasdaq, CQT, and OTCBB)](restapi/bars-all.md)

### Indexes

- [`GET` Value](restapi/indexvalue.md)
- [`GET` Snapshot](restapi/indexsnapshot.md)

### Exchange Traded Products (ETPs)

- [`GET` Value](restapi/etpvalue.md)
- [`GET` Snapshot](restapi/etpsnapshot.md)

### Options

- [`GET` Chain](restapi/chain.md)
- [`GET` Prices](restapi/prices.md)
- [`GET` Greeks and Vols U.S.](restapi/greeksandvols.md)

### Reference

- [`GET` All Symbols](restapi/symbols.md)
- [`GET` Symbol Details](restapi/symbol.md)
- [`GET` All Indexes](restapi/indexes.md)
- [`GET` Index Details](restapi/index.md)
- [`GET` Index Participants](restapi/indexparticipants.md)
- [`GET` All ETPs](restapi/etps.md)
- [`GET` ETP Details](restapi/etp.md)
- [`GET` Option Contracts](restapi/contracts.md)

## Versioning

The first part of the URI path specifies the API version, in the format v{version_number}. For example, version 1 of the API (most current) is accessible via: For example, version 1 of the API (most current) is accessible via:  `https://<base_url>/v1/`

## HTTP Response Codes

`200` `OK` The request was successful.

`400` `Bad Request` Your request is invalid.

`401` `Unauthorized` Your not entitled for requested data.

`404` `Not Found` The specified API endpoint could not be found.

`500` `Internal Server Error` We had a problem with our server. Try again later.

`503` `Service Unavailable` We're temporarily offline for maintenance. Try again later.

## Tutorial

We provide a [Postman](https://www.getpostman.com/) collection with a set of requests for the API. You will need an Nasdaq Cloud Data Service account with API access to run this tutorial. The Postman collection and environemnt files are available [here](restapi/postman).

## License

Code and documentation released under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)
