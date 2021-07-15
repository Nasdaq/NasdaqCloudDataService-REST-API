# Nasdaq Cloud Data Service (NCDS) - Real-time REST API

Nasdaq Cloud Data Service (NCDS) provides a modern and efficient method of delivery for realtime exchange data and other financial information. Data is made available through a suite of APIs, allowing for effortless integration of data from disparate sources, and a dramatic reduction in time to market for customer-designed applications. The API is highly scalable, and robust enough to support the delivery of real-time exchange data. Read our latest NCDS case study: <a href="https://www.nasdaq.com/docs/2021/05/13/1323-Q21_Unhedged%20NCDS%20Case%20Study_II-v2.pdf">Nasdaq Cloud Data Service Provides Real-Time Data with Efficiency and Scale to Fintech Newcomer Unhedged</a> 

## Table of Contents

- [Products Currently Available](#products-currently-available)
- [Getting Started](#getting-started)
- [Authentication](#suthentication)
- [API Resources](#api-resources)
- [Versioning](#versioning)
- [HTTP Response Codes](#http-response-codes)
- [Tutorial](#tutorial)
- [License](#License)

## Products Currently Available

### Equities

#### The Nasdaq Stock Market

- [Nasdaq Basic](https://www.nasdaq.com/solutions/nasdaq-basic)
- [Nasdaq Last Sale+](https://www.nasdaq.com/solutions/nasdaq-last-sale) 

#### Nasdaq BX

- [BX BBO](http://www.nasdaqtrader.com/Trader.aspx?id=bxbasic)
- [BX Last Sale](http://www.nasdaqtrader.com/Trader.aspx?id=BLS)

#### Nasdaq PSX

- [PSX BBO](http://www.nasdaqtrader.com/Trader.aspx?id=PLS)
- [PSX Last Sale](http://www.nasdaqtrader.com/Trader.aspx?id=psxbasic)

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

### Reference

- [`GET` All Symbols](restapi/symbols.md)
- [`GET` Symbol Details](restapi/symbol.md)

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
