# Activity

<aside class="warning">These methods are deprecated, please use <a href="#product">Product content</a> instead</aside>

**Activity** operations provide information on **Activity** products available in a point of sale. No availability information is included here, it is primarily content (images, position, categories, etc). 

All **GET** operations 
<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the `pointOfSalesId`</aside>

## Activity

```shell
curl -X GET 
  --header 'ApiKey: APIKEY132456789EWOK'
  --header 'Accept: application/json' 
  --header 'Accept-Language: en-US'
  'https://galaxy.citybreak.com/v5/api/activity/{pointOfSaleId}/20/0'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/activity/{pointOfSaleId}/20/0",
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
  "TotalResults": 25,
  "Items": [
    {
      "Id": "cbis:1324320",
      "Name": "Valley stars 7-9 years",
      "Content": {
        "PriceFrom": 1280,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5039905",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 141,
            "Name": "Prices from",
            "Value": "1280"
          },
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Valley stars 7-9 years"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Grouplessons for Valley stars 7-9 years, beginner level"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Beginner lessons where will learn skiing, stop and turn through fun activities. We will begin to handle the lifts. \r\n\r\nMust know: Nothing."
          }
        ],
        "Categories": null,
        "Geos": [
          {
            "Id": 105257,
            "Path": "[ALPINCO Hafjell och Kvitfjell]"
          },
          {
            "Id": 105629,
            "Path": "Hafjell & Kvitfjell"
          },
          {
            "Id": 105260,
            "Path": "Hafjell"
          }
        ],
        "Pois": [],
        "Position": {
          "Latitude": 61.2340708391529,
          "Longitude": 10.4462814331055
        }
      },
      "Occasions": [
        {
          "Start": "2017-12-18T00:00:00Z",
          "End": "2017-12-18T00:00:00Z",
          "Arena": null
        },
        {
          "Start": "2017-12-18T00:00:00Z",
          "End": "2017-12-18T00:00:00Z",
          "Arena": null
        },
        {
          "Start": "2017-12-18T00:00:00Z",
          "End": "2017-12-18T00:00:00Z",
          "Arena": null
        }
      ],
      "Children": []
    }
  ]
}   
```

Get details about Activity

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/activity/{pointOfSalesId}/{pageSize}/{page}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
pageSize | Size of the page.
page | The page.

## Product

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/activity/view/{pointOfSaleId}/{productId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/activity/view/{pointOfSaleId}/{productId}'",
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
  "Id": "cbis:1324320",
  "Name": "Valley stars 7-9 years",
  "Content": {
    "PriceFrom": 1280,
    "Images": [
      {
        "Uri": "//images.citybreak.com/image.aspx?ImageId=5039905",
        "IsMain": false,
        "Name": null,
        "Copyright": null,
        "Description": null
      }
    ],
    "Information": [
      {
        "Id": 141,
        "Name": "Prices from",
        "Value": "1280"
      },
      {
        "Id": 99,
        "Name": "Name",
        "Value": "Valley stars 7-9 years"
      },
      {
        "Id": 101,
        "Name": "Introduction",
        "Value": "Grouplessons for Valley stars 7-9 years, beginner level"
      },
      {
        "Id": 102,
        "Name": "Description",
        "Value": "Beginner lessons where will learn skiing, stop and turn through fun activities. We will begin to handle the lifts. \r\n\r\nMust know: Nothing."
      }
    ],
    "Categories": null,
    "Geos": [
      {
        "Id": 105257,
        "Path": "[ALPINCO Hafjell och Kvitfjell]"
      },
      {
        "Id": 105629,
        "Path": "Hafjell & Kvitfjell"
      },
      {
        "Id": 105260,
        "Path": "Hafjell"
      }
    ],
    "Pois": [],
    "Position": {
      "Latitude": 61.2340708391529,
      "Longitude": 10.4462814331055
    }
  },
  "Occasions": [
    {
      "Start": "2017-12-18T00:00:00Z",
      "End": "2017-12-18T00:00:00Z",
      "Arena": null
    },
    {
      "Start": "2017-12-18T00:00:00Z",
      "End": "2017-12-18T00:00:00Z",
      "Arena": null
    },
    {
      "Start": "2017-12-18T00:00:00Z",
      "End": "2017-12-18T00:00:00Z",
      "Arena": null
    }
  ],
  "Children": []
}
```

Get details and content about a specific Citybreak product, the requests requires that you have both a Point of Sale Id and a valid Product Id

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/activity/view/{pointOfSalesId}/{productId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
productId | The Id of the product you wish to retrieve.


