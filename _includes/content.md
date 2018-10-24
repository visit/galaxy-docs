# Content

> Content

**Content** calls provide information about several content types used by your org, Attributes, GeoNodes, Points of Interest and Categories. This can be useful when creating content filters on your site as each of these types are suitable for content filtering on **Availability** searches. As with other calls, these are available in the languages your organisation supports and has translated (for non-system content). You need the relevant **Point of Sale Id** for all these calls.

All **GET** operations 
<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the **{pointOfSalesId}**</aside>
## Attributes

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v3/api/content/attribute/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/content/attribute/{pointOfSaleId}",
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
    "Id": 99,
    "Name": "Name",
    "Type": "String"
  },
  {
    "Id": 101,
    "Name": "Introduction",
    "Type": "String"
  },
  {
    "Id": 102,
    "Name": "Description",
    "Type": "String"
  },
  {
    "Id": 103,
    "Name": "Directions",
    "Type": "String"
  },
  {
    "Id": 104,
    "Name": "Opening hours",
    "Type": "String"
  },
   {
    "Id": 102728,
    "Name": "1 level apartment",
    "Type": "Boolean"
  },
  {
    "Id": 102729,
    "Name": "2 level apartment",
    "Type": "Boolean"
  },
  {
    "Id": 102732,
    "Name": "Cleaning included",
    "Type": "Boolean"
  },
  {
    "Id": 102733,
    "Name": "Shop",
    "Type": "Boolean"
  },
  {
    "Id": 102734,
    "Name": "Ski buses",
    "Type": "Boolean"
  }
]
```

Get localised Attribute information.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/content/attribute`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.

## GeoNodes

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v3/api/content/geo/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/content/geo/{pointOfSaleId}",
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
{
  "Id": 69962,
  "Children": [
    {
      "Id": 105634,
      "Children": []
    },
    {
      "Id": 106922,
      "Children": [
        {
          "Id": 106923,
          "Children": []
        }
      ]
    },
    {
      "Id": 70494,
      "Children": [
        {
          "Id": 70505,
          "Children": [
            {
              "Id": 70495,
              "Children": []
            }
          ]
        }
      ]
    }
  ]
}
```

Get the GeoNode tree. This is a nested list of client-defined geo-locations that can be associated with products, e.g. a hotel in Gothenburg might have both the node representing Sweden and the node representing Gothenburg included in its content, enabling you to filter on either.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/content/geo`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.

## Category

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v3/api/content/category/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/content/category/{pointOfSaleId}",
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
{
  "Id": 5946,
  "Children": [
    {
      "Id": 30701,
      "Children": [
        {
          "Id": 26219,
          "Children": [
            {
              "Id": 26218,
              "Children": []              
            }
          ]
        },
        {
          "Id": 26217,
          "Children": []
        },
        {
          "Id": 26220,
          "Children": [
            {
              "Id": 30610,
              "Children": []
            }
          ]
        }
      ],
    }
  ]
}
```

Get the Category tree. This is a nested list of client-defined categories that can be associated with products, e.g. a hotel might have both the node representing Hotel and the child node representing Boutique Hotel included in its content, enabling you to filter on either.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/content/category`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.

## Point Of Interest

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v3/api/content/poi/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/content/poi/{pointOfSaleId}",
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
    "Id": 16,
    "Name": "Leksand",
    "Position": {
      "Longitude": 15.0032043457031,
      "Latitude": 60.7338905334473
    }
  },
  {
    "Id": 17,
    "Name": "Mora (Mora-Siljan flygplats)",
    "Position": {
      "Longitude": 14.5049390792847,
      "Latitude": 60.958568572998
    }
  },
  {
    "Id": 18,
    "Name": "Borlänge (Dala Airport)",
    "Position": {
      "Longitude": 15.5104637145996,
      "Latitude": 60.4233436584473
    }
  },
  {
    "Id": 8305,
    "Name": "Inlandsbanan",
    "Position": {
      "Longitude": 16.2033634185791,
      "Latitude": 64.113899230957
    }
  },
]
```

Get a list of Points of Interest. This is a mixed list of system and client-defined geographic Points of Interest that can be associated with products, e.g. a hotel might be nearby a train station or a key landmark and this information can be associated with the product and used for content filtering.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/content/poi`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.

## Languages

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
'https://galaxy.citybreak.com/v3/api/content/language/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/content/language/{pointOfSaleId}",
{
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json"
  }  
});
```

> Example of response:

```json
[
  "en-us",
  "sv-se",
  "fr-fr"
]
```

Get a list of languages available for a given point of sales.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/content/language`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
