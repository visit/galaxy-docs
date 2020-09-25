# Transport

**Transport** operations provide information on **Transport** products available in a point of sale. No availability information is included here, it is primarily content (price groups, routes, etc).

All **GET** operations 
<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the `pointOfSalesId`</aside>

## Price Groups

```shell
curl -X GET 
  --header 'ApiKey: APIKEY132456789EWOK'
  --header 'Accept: application/json' 
  --header 'Accept-Language: en-US'
  'https://galaxy.citybreak.com/v5/api/transport/priceGroups/{pointOfSalesId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/transport/priceGroups/{pointOfSalesId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
	"Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "PersonPriceGroups": [
    {
      "Code": "997",
      "Name": "Adult",
      "MinAge": 0,
      "MaxAge": 2147483647
    },
    {
      "Code": "1037",
      "Name": "Child 4-11",
      "MinAge": 4,
      "MaxAge": 11
    },
    {
      "Code": "1166",
      "Name": "Child 0-3",
      "MinAge": 0,
      "MaxAge": 3
    },
    {
      "Code": "1359",
      "Name": "Teens 12-15",
      "MinAge": 12,
      "MaxAge": 15
    }
  ],
  "VehiclePriceGroups": [
    {
      "Code": "998",
      "Name": "Car max 1.85m x 5m "
    },
    {
      "Code": "1032",
      "Name": "Motorhome max 4m x 7m"
    },
    {
      "Code": "1034",
      "Name": "Motorcycle"
    },
    {
      "Code": "1035",
      "Name": "Motorcycle with sidecar"
    },
    {
      "Code": "1036",
      "Name": "Bicycle"
    },
    {
      "Code": "1160",
      "Name": "Car max 2.20m x 6m"
    },
    {
      "Code": "1161",
      "Name": "Motorhome max 4m x 10m"
    }
  ]
}
```

Get lists of person and vehicle price groups that could be available from the specified point of sales, with full details about them

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/transport/priceGroups/{pointOfSalesId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
Accept-Language | The language culture (e.g en-us)

## Price Groups for product

```shell
curl -X GET 
  --header 'ApiKey: APIKEY132456789EWOK'
  --header 'Accept: application/json' 
  --header 'Accept-Language: en-US'
  'https://galaxy.citybreak.com/v5/api/transport/priceGroups/{pointOfSalesId}/{productId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/transport/priceGroups/{pointOfSalesId}/{productId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
	"Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "PersonPriceGroups": [
    {
      "Code": "997",
      "Name": "Adult",
      "MinAge": 0,
      "MaxAge": 2147483647
    },
    {
      "Code": "1037",
      "Name": "Child 4-11",
      "MinAge": 4,
      "MaxAge": 11
    },
    {
      "Code": "1166",
      "Name": "Child 0-3",
      "MinAge": 0,
      "MaxAge": 3
    },
    {
      "Code": "1359",
      "Name": "Teens 12-15",
      "MinAge": 12,
      "MaxAge": 15
    }
  ],
  "VehiclePriceGroups": [
    {
      "Code": "998",
      "Name": "Car max 1.85m x 5m "
    },
    {
      "Code": "1032",
      "Name": "Motorhome max 4m x 7m"
    },
    {
      "Code": "1034",
      "Name": "Motorcycle"
    },
    {
      "Code": "1035",
      "Name": "Motorcycle with sidecar"
    },
    {
      "Code": "1036",
      "Name": "Bicycle"
    },
    {
      "Code": "1160",
      "Name": "Car max 2.20m x 6m"
    },
    {
      "Code": "1161",
      "Name": "Motorhome max 4m x 10m"
    }
  ]
}
```

Get lists of person and vehicle price groups for a specific product that is available from the specified point of sales, with full details about them

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/transport/priceGroups/{pointOfSalesId}/{productId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
productId | The product identifier.
Accept-Language | The language culture (e.g en-us)

## Routes

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/transport/routes/{pointOfSalesId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/transport/routes/{pointOfSalesId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
   "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "Locations": [
    {
      "Code": "25142",
      "Name": "Oslo",
      "City": null,
      "Country": "NO",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25132",
      "Name": "Copenhagen",
      "City": null,
      "Country": "DK",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25130",
      "Name": "Amsterdam",
      "City": null,
      "Country": "NL",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25140",
      "Name": "Newcastle",
      "City": null,
      "Country": "GB",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25852",
      "Name": "Frederikshavn",
      "City": null,
      "Country": "DK",
      "NameScheme": "DFDS"
    }
  ],
  "Routes": [
    {
      "DepartureLocationCode": "25142",
      "ArrivalLocationCode": "25132",
      "Description": null,
      "AllowRoundtrip": true,
      "AllowOneWay": true
    },
    {
      "DepartureLocationCode": "25130",
      "ArrivalLocationCode": "25140",
      "Description": null,
      "AllowRoundtrip": true,
      "AllowOneWay": true
    },
    {
      "DepartureLocationCode": "25142",
      "ArrivalLocationCode": "25852",
      "Description": null,
      "AllowRoundtrip": true,
      "AllowOneWay": true
    },
    {
      "DepartureLocationCode": "25852",
      "ArrivalLocationCode": "25142",
      "Description": null,
      "AllowRoundtrip": false,
      "AllowOneWay": true
    }
  ]
}
```

Get list of locations and routes that could be available from the specified point of sales, with full details about them

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/transport/routes/{pointOfSalesId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
Accept-Language | The language culture (e.g en-us)

## Routes for product

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/transport/routes/{pointOfSalesId}/{productId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/transport/routes/{pointOfSalesId}/{productId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
   "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "Locations": [
    {
      "Code": "25142",
      "Name": "Oslo",
      "City": null,
      "Country": "NO",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25132",
      "Name": "Copenhagen",
      "City": null,
      "Country": "DK",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25130",
      "Name": "Amsterdam",
      "City": null,
      "Country": "NL",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25140",
      "Name": "Newcastle",
      "City": null,
      "Country": "GB",
      "NameScheme": "DFDS"
    },
    {
      "Code": "25852",
      "Name": "Frederikshavn",
      "City": null,
      "Country": "DK",
      "NameScheme": "DFDS"
    }
  ],
  "Routes": [
    {
      "DepartureLocationCode": "25142",
      "ArrivalLocationCode": "25132",
      "Description": null,
      "AllowRoundtrip": true,
      "AllowOneWay": true
    },
    {
      "DepartureLocationCode": "25130",
      "ArrivalLocationCode": "25140",
      "Description": null,
      "AllowRoundtrip": true,
      "AllowOneWay": true
    },
    {
      "DepartureLocationCode": "25142",
      "ArrivalLocationCode": "25852",
      "Description": null,
      "AllowRoundtrip": true,
      "AllowOneWay": true
    },
    {
      "DepartureLocationCode": "25852",
      "ArrivalLocationCode": "25142",
      "Description": null,
      "AllowRoundtrip": false,
      "AllowOneWay": true
    }
  ]
}
```

Get list of locations and routes for a specific product that could be available from the specified point of sales, with full details about them

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/transport/routes/{pointOfSalesId}/{productId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
productId | The product identifier.
Accept-Language | The language culture (e.g en-us)


## Locations

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/transport/locations/{pointOfSalesId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/transport/locations/{pointOfSalesId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
   "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "DepartureLocations": [
    {
      "Code": "25130",
      "Name": "Amsterdam",
      "City": null,
      "Country": "NL",
      "NameScheme": "DFDS",
      "Type": "Seaport"
    },
    {
      "Code": "25142",
      "Name": "Oslo",
      "City": null,
      "Country": "NO",
      "NameScheme": "DFDS",
      "Type": "Seaport"
    },
    {
      "Code": "25852",
      "Name": "Frederikshavn",
      "City": null,
      "Country": "DK",
      "NameScheme": "DFDS",
      "Type": "Seaport"
    }
  ],
  "ArrivalLocations": [
    {
      "Code": "25132",
      "Name": "Copenhagen",
      "City": null,
      "Country": "DK",
      "NameScheme": "DFDS",
      "Type": "Seaport"
    },
    {
      "Code": "25140",
      "Name": "Newcastle",
      "City": null,
      "Country": "GB",
      "NameScheme": "DFDS",
      "Type": "Seaport"
    },
    {
      "Code": "25142",
      "Name": "Oslo",
      "City": null,
      "Country": "NO",
      "NameScheme": "DFDS",
      "Type": "Seaport"
    },
    {
      "Code": "25852",
      "Name": "Frederikshavn",
      "City": null,
      "Country": "DK",
      "NameScheme": "DFDS",
      "Type": "Seaport"
    }
  ]
}
```

Get details about locations that could be available from the specified point of sales, with full details about them

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/transport/locations/{pointOfSalesId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
Accept-Language | The language culture (e.g en-us)


