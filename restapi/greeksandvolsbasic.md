## Nasdaq Greeks and Implied Volatility Powered by Basic

Option Greeks, Implied Volatility, and Theoretical Price for the associated symbol. 

##### Endpoint

`GET` `https://<base_url>/v1/nasdaq/<offset>/greeksandvolsusbasic/<symbol>`

#### URI Parameters

`<source>` - `nasdaq`

`<offset>` -  Real-time data; acceptable values: realtime, delayed (currently only realtime is offered)

`<symbol>` - Unique identifier of the options contract

#### Headers

`"Authorization: Bearer <token>"`

#### Request Body

none

#### Response Body

```
[
  {
    “t”: “string”, 
    “i”: “string”,   
    “u”: “string”, 
    “d”: “number”  
    “g”: “number” 
    “vg”: “number” 
    “tt”: “number”  
    “r”: “number” 
    “iv”: “number”   
    "tp”: “number” 
  }
]
```

| Name | Field | Type | Description |
|-------|------|------|-------------|
|timestamp|t|string|The timestamp for all values.|
|option/identifier|i|string|Unique identifier of the options contract: Symbol + Expiration Date + Option Type + Strike Price, using OSI symbology for all US options; see https://en.wikipedia.org/wiki/Option_symbol|
|underlying|u|string|Underlying symbol associated with the Option.|
|delta|d|number|Compares the rate of change between the underlying asset's price and the option instrument’s price.|
|Gamma|g|number|Provides the rate of change for an option instrument’s delta value based on a single point move in the underliers price.|
|Vega|vg|number|Measures an option instrument’s change in price relative to a single point move in implied volatility of the underlying instrument. |
|Theta|tt|number|Represents the rate of decline in the value of an option instrument over time as the expiration date approaches. |
|Rho|r|number|Measures the price change for an option instrument relative to a change in the risk-free rate of interest. |
|Implied Volatility|iv|number|Provides the market forecast of expected movements in the underlying instrument over the duration of the option instrument’s life. |
|Theoretical Price|tp|number|Provides an estimated price of an option instrument that can be used alongside market prices. |

---


### Example

#### Request

```
curl --request GET \
  --url https://dev.restapi.clouddataservice.nasdaq.com/v1/nasdaq/realtime/greeksandvolsus/BRKB%2520%2520250627C00270000 \
  --header 'authorization: Bearer {{AuthorizationToken}}' 
  --header 'content-type: application/json'
```

#### Response

```
[
  {
    "u": "AAPL.O",
    "d": 0.5976895209869326,
    "g": 0.1812382635080212,
    "vg": 0.040720051256926126,
    "tt": -0.3208365923907447,
    "r": 0.003785521215604603,
    "iv": 0.20281799478887522,
    "tp": 1.1320738969929778,
    "t": "2023-05-26T09:50:02.088",
    "i": "AAPL  230526C00172500"
  }
]
```
