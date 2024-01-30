# Output Filter

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
    "PointOfSalesId": 0,
    "Arrival": "2017-10-14",
    "Departure": "2017-10-15",
    "Currency": "SEK",
    "PageSize": 20,
    "PersonConfigurations": [
      {
        "Adults": 1,
        "ChildrenAges": [
          0
        ] 
      }
    ],
    "OutputFilter": { 
      "Attributes": [
        0
      ],
      "Categories": true,
      "Geos": true,
      "Pois": true,
      "Position": true,
      "Images": true
    }
 }' 'https://galaxy.citybreak.com/v5/api/availability/accommodation'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/accommodation",
{
	method: "POST",
	headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 0,
    "Arrival": "2017-10-14",
    "Departure": "2017-10-15",
    "Currency": "SEK",
    "PageSize": 20,
    "PersonConfigurations": [
      {
        "Adults": 1,
        "ChildrenAges": [
          0
        ] 
      }
    ],
    "OutputFilter": { 
      "Attributes": [
        99
      ],
      "Categories": false,
      "Geos": true,
      "Pois": false,
      "Position": true,
      "Images": true
    }
	})  
});
```

> Example of response:

```json
{
  "AccommodationSearch": {
    "PointOfSalesId": 0,
    "Arrival": "2017-10-14T00:00:00Z",
    "Departure": "2017-10-15T00:00:00Z",
    "Currency": "SEK",
    "PageSize": 20,
    "Page": 1,
    "Sort": {
      "Order": 0,
      "Field": "Price"
    },
    "PersonConfigurations": [
      {
        "Adults": 1,
        "ChildrenAges": [
          0
        ]
      }
    ],
    "ContentFilter": null,
    "OutputFilter": null
  },
  "Accommodations": [
    {
      "Id": "cbis:12345",
      "Name": "BookVisit Hotel",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=101010101",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=101010101",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "BookVisit Hotel"
          }
        ],
        "Categories": null,
        "Geos": [
          {
            "Id": 12345,
            "Path": "Sweden"
          },
          {
            "Id": 12346,
            "Path": "Vastra Gotaland"
          },
          {
            "Id": 12347,
            "Path": "Goteborg"
          }
        ],
        "Pois": null,
        "Position": {
          "Latitude": 57.7089,
          "Longitude": 11.9746
        }
      },
      "Placements": [
        {
          "Price": {
            "Price": 450,
            "TotalPersons": 2,
            "Currency": "SEK",
            "DateStart": "2017-10-14T00:00:00Z",
            "DateEnd": "2017-10-15T00:00:00Z"
          },
          "Placements": [
            {
              "Name": "Dubbelrum med xbädd ÖSD",
              "Content": {
                "PriceFrom": null,
                "Images": [],
                "Information": [
                  {
                    "Id": 99,
                    "Name": "Name",
                    "Value": "Dubbelrum med xbädd ÖSD"
                  }
                ],
                "Categories": null,
                "Geos": null,
                "Pois": null,
                "Position": null
              },
              "IncludedAddons": [],
              "MaxPopopulation": 3,
              "MinPopulation": 1,
              "ExtraBeds": 1,
              "PersonConfiguration": {
                "Adults": 1,
                "ChildrenAges": [
                  1
                ]
              },
              "PricePeriods": [
                {
                  "DateStart": "2017-10-14T00:00:00",
                  "DateEnd": "2017-10-15T00:00:00",
                  "AdultPrice": 300,
                  "ChildPrice": 150,
                  "TotalPrice": 450,
                  "Currency": "SEK"
                }
              ],
              "BookingConditions": {
                "Name": null,
                "Terms": null
              }
            }
          ],
          "BookingKey": "18-A"
        }
      ],
      "TotalResults": 1
    }
  ],
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh",
  "ExpirationDate": "2018-09-15T09:15:46.0619347Z",
  "TotalResults": 1
}
```

Output filters used in Availability queries. All the properties in the filter relate to content. Each property is optional but Attributes is an inclusive filter, if no attributes to filter on are provided all attributes are sent, while the boolean properties such as Categories default to false (which will return null for that content property)

<code class ="center-column">
{
  "OutputFilter": { // Optional
    // List of ints - Optional, defaults to showing all attributes if not included
    "Attributes": [ 
      0
    ],
    "Categories": true, // bool - Optional, defaults to false if not included
    "Geos": true, // bool - Optional, defaults to false if not included
    "Pois": true, // bool - Optional, defaults to false if not included
    "Position": true, // bool - Optional, defaults to false if not included
    "Images": true // bool - Optional, defaults to true if not included, for backward compatibility
  }
}
</code>

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
Attributes | int[] | List of ids of product attribute content to display.
Categories | bool | If true display product Category content
Geos | bool | If true display product Geonode content
Pois | bool | If true display Position of Interest content
Position | bool | If true display product Position lat and long
Images | bool | If true display product Image content
