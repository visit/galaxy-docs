# Points of Sale

> Content

**Points of Sale** are the distribution channels controlled by an Citybreak Organisation. An API key may give access to multiple Points of Sale, each with it's own rate and currency information and selection of available products. Having a valid Point of Sale Id is important for most other queries in the API

All **GET** operations

## Point Of Sales

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.test.citybreak.com/api/pointofsales'

```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/pointofsales",
{
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
	 "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
[
  {
    "Id": 1,
    "Name": "Online"
  },
  {
    "Id": 2,
    "Name": "online viktors hotell 3"
  },
  {
    "Id": 5,
    "Name": "callcenter test"
  },
  {
    "Id": 9,
    "Name": "Veras Call Center"
  }
]
```

Get the points of sale available to the current API Key. 

### HTTP Request

`GET https://galaxy.citybreak.com/api/pointofsales`

## Currencies

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.test.citybreak.com/api/pointofsales/currencies/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/pointofsales/currencies/{pointOfSaleId}",
{
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
   "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
[
  "DKK",
  "SEK",
  "NOK",
  "EUR"
]
```

Get currencies available for a given Point of Sale. Availability searches will require a currency for a valid search.

### HTTP Request

`GET https://galaxy.citybreak.com/api/pointofsales/currencies`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
