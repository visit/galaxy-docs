# Accommodation

> Accommodation

```json
{
  "Fix":"fix this"
}
```

**Accommodation** operations provide information on **Accommodation** products available in a point of sale. No availability information is included here, it is primarily content (images, position, categories, etc).

All **GET** operations *NB: if using the Visit Test Organisation API Key you can use 17692 as the pointOfSaleId*

## Accommodation

```shell
curl -X GET 
  --header 'ApiKey: APIKEY132456789EWOK'
  --header 'Accept: application/json' 
  --header 'Accept-Language: en-US'
  'https://galaxy.test.citybreak.com/api/accommodation/{pointOfSaleId}/20/0'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/accommodation/{pointOfSaleId}/20/0",
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
  "Page": 0,
  "PageSize": 20,
  "TotalResults": 1,
  "Items": [
    {
      "Id": 1222681,
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

`GET https://galaxy.test.citybreak.com/api/accommodation`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
pageSize | Size of the page.
page | The page.

