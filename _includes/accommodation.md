# Accommodation

<aside class="warning">These methods are deprecated, please use <a href="#content">Product content</a> instead</aside>

**Accommodation** operations provide information on **Accommodation** products available in a point of sale. No availability information is included here, it is primarily content (images, position, categories, etc).

All **GET** operations 
<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the `pointOfSalesId`</aside>

## Accommodation

```shell
curl -X GET 
  --header 'ApiKey: APIKEY132456789EWOK'
  --header 'Accept: application/json' 
  --header 'Accept-Language: en-US'
  'https://galaxy.citybreak.com/v5/api/accommodation/{pointOfSaleId}/{pageSize}/{page}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/accommodation/{pointOfSaleId}/{pageSize}/{page}",
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
  "Page": 0,
  "PageSize": 20,
  "TotalResults": 1,
  "Items": [
    {
      "Id": "cbis:12345",
      "Name": "BookVisit Hotel",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=4136104",
            "IsMain": true,
            "Name": null,
            "Copyright": "",
            "Description": null
          },
        ],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "BookVisit Hotel"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Leading e-commerce platform for the DMO and individual hotels in the Nordics."
          },
        ],
        "Categories": null,
        "Geos": [
          {
            "Id": 69962,
            "Path": null
          },
        ],
        "Pois": [],
        "Position": {
          "Latitude": 57.7039005352791,
          "Longitude": 11.9626625079345
        }
      },
      "Children": [
        {
          "Id": "pt:355468",
          "Name": "BookVisit Hotel BookVisit",
          "Content": {
            "PriceFrom": null,
            "Images": null,
            "Information": null,
            "Categories": null,
            "Geos": null,
            "Pois": null,
            "Position": null
          }
        }
      ]
    }
  ]
}
```

Get details about Accommodation

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/accommodation/view/{pointOfSalesId}/{page}/{pageSize}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
pageSize | Size of the page.
page | The page (starting at 0).

## Product

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/accommodation/{pointOfSalesId}/{pageSize}/{page}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/accommodation/view/{pointOfSaleId}/{productId}'",
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
  "Id": "cbis:12345",
  "Name": "BookVisit Hotel",
  "Content": {
    "PriceFrom": 0,
    "Images": [
      {
        "Uri": "//images.citybreak.com/image.aspx?ImageId=4136104",
        "IsMain": true,
        "Name": null,
        "Copyright": "",
        "Description": null
      },
    ],
    "Information": [
      {
        "Id": 99,
        "Name": "Name",
        "Value": "BookVisit Hotel"
      },
      {
        "Id": 101,
        "Name": "Introduction",
        "Value": "Leading e-commerce platform for the DMO and individual hotels in the Nordics."
      },
    ],
    "Categories": null,
    "Geos": [
      {
        "Id": 69962,
        "Path": null
      },
    ],
    "Pois": [],
    "Position": {
      "Latitude": 57.7039005352791,
      "Longitude": 11.9626625079345
    }
  },
  "Children": [
    {
      "Id": "pt:542664"
      "Name": "BookVisit Hotel BookVisit",
      "Content": {
        "PriceFrom": null,
        "Images": null,
        "Information": null,
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ]
}
```

Get details and content about a specific Citybreak product, the requests requires that you have both a Point of Sale Id and a valid Product Id

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/accommodation/view/{pointOfSalesId}/{productId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
productId | The Id of the product you wish to retrieve.


