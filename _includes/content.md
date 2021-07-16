# Content

**Content** calls provide information about several content types used by your org, Attributes, GeoNodes, Points of Interest and Categories. This can be useful when creating content filters on your site as each of these types are suitable for content filtering on **Availability** searches. As with other calls, these are available in the languages your organisation supports and has translated (for non-system content). You need the relevant `pointOfSalesId` for all these calls.

<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the `pointOfSalesId`</aside>

## Product content


```shell
curl -X POST
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d 
'{
  "PointOfSalesId": 16697,
  "PageSize": 50,
  "Page": 0,
  "ContentFilter": {
    "Ids": [
      "cbis:1714422"
    ]
  }
}' 
'https://galaxy.citybreak.com/v5/api/content/product'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/content/product",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 16697,
    "PageSize": 50,
    "Page": 0,
    "ContentFilter": {
      "Ids": [
        "cbis:1714422"
      ]
    }
  })  
});
```

> Example of response:

```json
{
  "Page": 0,
  "PageSize": 50,
  "TotalResults": 1,
  "Items": [
    {
      "Id": "cbis:1714422",
      "Name": "Scandic Hafjell",
      "ProductType": "Accommodation",
      "Content": {
        "Id": "cbis:1714422",
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860262",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860263",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860264",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860265",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860268",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860269",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860270",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860271",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860272",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860273",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5860274",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=6661261",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=6661262",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=6661263",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 122,
            "Name": "Country (address)",
            "Value": "162"
          },
          {
            "Id": 130,
            "Name": "Number of rooms",
            "Value": "210"
          },
          {
            "Id": 131,
            "Name": "Number of floors",
            "Value": "3"
          },
          {
            "Id": 132,
            "Name": "Number of conference rooms",
            "Value": "12"
          },
          {
            "Id": 133,
            "Name": "Number of bars",
            "Value": "1"
          },
          {
            "Id": 151,
            "Name": "Classification",
            "Value": "4"
          },
          {
            "Id": 910,
            "Name": "UrlName",
            "Value": "Scandic_Hafjell_1714422"
          },
          {
            "Id": 117,
            "Name": "Street address 1",
            "Value": "Hunderveien 1 "
          },
          {
            "Id": 120,
            "Name": "Postal code",
            "Value": "2636"
          },
          {
            "Id": 121,
            "Name": "City (address)",
            "Value": "Øyer"
          },
          {
            "Id": 134,
            "Name": "Built in year",
            "Value": "1991"
          },
          {
            "Id": 135,
            "Name": "Last renovated year",
            "Value": "2017"
          },
          {
            "Id": 142,
            "Name": "Phone number (reception)",
            "Value": "61277777"
          },
          {
            "Id": 144,
            "Name": "Country code (reception)",
            "Value": "47"
          },
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Scandic Hafjell"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Hafjell is the perfect starting point for activities and leisure."
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "The perfect meeting point for leisure and activities is just 2,5 hours from Oslo, with a central location in Hafjell and proximity to exciting activities. The hotel has many family rooms, and great facilities for entertaining young and old.\r\n\r\nThe hotel offers a barception and 24-hour shop throughout the year, with a selection of light meals, snacks and beverages. With an indoor pool, large playroom, sauna and modern fitness room, we have something for everyone.\r\n \r\nHafjell is the perfect starting point for activities and leisure. Our hotel is located only 700 metres from one of Norway’s largest alpine skiing facilities, Hafjell alpinsenter, and only 15 minutes from Lillehammer. This makes us the natural choice if you're looking for an active and exciting holiday. Hunderfossen family park, the bobsleigh and luge track, and great hiking trails make Hafjell a great destination, both in summer and winter."
          },
          {
            "Id": 103,
            "Name": "Directions",
            "Value": "Scandic Hafjell is located 2.5 hours from Oslo, and only 15 minutes north of Lillehammer. The hotel sits next to the highway E6, only 700 meters from Hafjell Alpine Centre. \r\n\r\nIf you wish to use public transport, we recommend taking the train to Lillehammer, and bus line 242 to Hafjell from Lillehammer. \r\nPlease see www.entur.no and www.innlandstrafikk.no for information and departure times."
          },
          {
            "Id": 100036,
            "Name": "Disability friendly",
            "Value": "True"
          },
          {
            "Id": 100037,
            "Name": "Pets allowed",
            "Value": "False"
          },
          {
            "Id": 100038,
            "Name": "Elevator",
            "Value": "True"
          },
          {
            "Id": 100039,
            "Name": "Parking nearby",
            "Value": "True"
          },
          {
            "Id": 100040,
            "Name": "Indoor pool",
            "Value": "True"
          },
          {
            "Id": 100043,
            "Name": "Sauna",
            "Value": "True"
          },
          {
            "Id": 100053,
            "Name": "Washing machine",
            "Value": "False"
          },
          {
            "Id": 100059,
            "Name": "TV",
            "Value": "False"
          },
          {
            "Id": 100062,
            "Name": "Refrigerator",
            "Value": "False"
          },
          {
            "Id": 100063,
            "Name": "Microwave",
            "Value": "False"
          },
          {
            "Id": 100071,
            "Name": "Fridge ",
            "Value": "False"
          },
          {
            "Id": 100074,
            "Name": "Dishwasher",
            "Value": "False"
          },
          {
            "Id": 100086,
            "Name": "Children's playground",
            "Value": "True"
          },
          {
            "Id": 100187,
            "Name": "Non smoking rooms",
            "Value": "True"
          },
          {
            "Id": 100188,
            "Name": "Non smoking",
            "Value": "False"
          },
          {
            "Id": 100208,
            "Name": "Allergy friendly room",
            "Value": "True"
          },
          {
            "Id": 100237,
            "Name": "Jacuzzi",
            "Value": "False"
          },
          {
            "Id": 100502,
            "Name": "Alpint",
            "Value": "True"
          },
          {
            "Id": 100540,
            "Name": "Billiard",
            "Value": "True"
          },
          {
            "Id": 100545,
            "Name": "Golf",
            "Value": "True"
          },
          {
            "Id": 100592,
            "Name": "Facilities for people with allergies",
            "Value": "False"
          },
          {
            "Id": 100599,
            "Name": "24 hours check-in",
            "Value": "True"
          },
          {
            "Id": 100606,
            "Name": "Breakfast",
            "Value": "True"
          },
          {
            "Id": 100624,
            "Name": "Air condition",
            "Value": "True"
          },
          {
            "Id": 100629,
            "Name": "Terrace",
            "Value": "False"
          },
          {
            "Id": 100635,
            "Name": "Fireplace",
            "Value": "False"
          },
          {
            "Id": 100752,
            "Name": "Luggage room",
            "Value": "True"
          },
          {
            "Id": 100767,
            "Name": "Mountain hiking",
            "Value": "True"
          },
          {
            "Id": 100826,
            "Name": "Close to mountains",
            "Value": "True"
          },
          {
            "Id": 100899,
            "Name": "Skibod",
            "Value": "True"
          },
          {
            "Id": 100928,
            "Name": "Games room",
            "Value": "True"
          },
          {
            "Id": 100929,
            "Name": "Ski in/Ski out",
            "Value": "False"
          },
          {
            "Id": 101383,
            "Name": "Indoor parking",
            "Value": "False"
          },
          {
            "Id": 101395,
            "Name": "Outdoor parking",
            "Value": "False"
          },
          {
            "Id": 101598,
            "Name": "All public areas non-smoking",
            "Value": "True"
          },
          {
            "Id": 101830,
            "Name": "Tumble dryer",
            "Value": "False"
          },
          {
            "Id": 101845,
            "Name": "WIFI",
            "Value": "True"
          },
          {
            "Id": 102045,
            "Name": "Close to center",
            "Value": "True"
          },
          {
            "Id": 102124,
            "Name": "Hiking",
            "Value": "False"
          },
          {
            "Id": 102267,
            "Name": "Snackbar",
            "Value": "True"
          },
          {
            "Id": 102272,
            "Name": "Cycling",
            "Value": "True"
          },
          {
            "Id": 102276,
            "Name": "Resort",
            "Value": "True"
          },
          {
            "Id": 102711,
            "Name": "Downhill biking",
            "Value": "False"
          },
          {
            "Id": 102712,
            "Name": "ski in/ ski out through transport slope",
            "Value": "False"
          }
        ],
        "Categories": [
          {
            "Id": 32039,
            "Path": "ALPINCO Hafjell och Kvitfjell"
          },
          {
            "Id": 32042,
            "Path": "Accommodation"
          },
          {
            "Id": 32062,
            "Path": "Hotels"
          }
        ],
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
          },
          {
            "Id": 105257,
            "Path": "[ALPINCO Hafjell och Kvitfjell]"
          },
          {
            "Id": 105629,
            "Path": "Hafjell & Kvitfjell"
          },
          {
            "Id": 105525,
            "Path": "Lillehammer"
          },
          {
            "Id": 105526,
            "Path": "Øyer"
          }
        ],
        "Pois": [],
        "Position": {
          "Latitude": 61.2417171,
          "Longitude": 10.4379985
        }
      },
      "Children": [
        {
          "Id": "pt:520359",
          "Name": "Scandic Hafjell BookVisit",
          "ProductType": "Accommodation",
          "Content": {
            "Id": null,
            "Images": [],
            "Information": [
              {
                "Id": 99,
                "Name": "Name",
                "Value": "Scandic Hafjell BookVisit"
              },
              {
                "Id": 101,
                "Name": "Introduction",
                "Value": null
              },
              {
                "Id": 102,
                "Name": "Description",
                "Value": null
              }
            ],
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

This is a POST request that requires a filter with some mandatory properties, such as PointOfSalesId, PageSize and Page.
The filter can also include content filtering, such as only including those products associated with a particular CBIS category. Content filtering possibilities can be found in the <a href="#content-filter">Content Section</a>. 
The filter can also include the list of specific product types which can be searched for, such as "Accommodation, "Transport" or "Activity".
You can see a bare minimum version of this search in the examples.
The most important return value in this response is the `ProductType` that suggests the user which endpoints to use for a specific product. 

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/content/product`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 0,  => int - Mandatory 
  "PageSize": 0,        => int - Mandatory
  "Page": 0,            => int - Mandatory
  "ProductTypes": [     => Optional - list of possible product types to Search.
    "Accommodation"     => Allowed values: "Accommodation", "Activity" and "Transport"
  ],
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a> for more info.
  }
}
</code>

## Attributes

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v5/api/content/attributes/{PointOfSalesId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/content/attributes/{PointOfSalesId}",
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

`GET https://galaxy.citybreak.com/v5/api/content/attribute/{pointOfSaleId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId  |  The point of sales identifier.
Accept-Language | The language culture (e.g en-us)

## GeoNodes

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v5/api/content/geo/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/content/geo/{pointOfSaleId}",
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

`GET https://galaxy.citybreak.com/v5/api/content/geo/{pointOfSaleId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId  |  The point of sales identifier.
Accept-Language | The language culture (e.g en-us)

## Category

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v5/api/content/category/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/content/category/{pointOfSaleId}",
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

`GET https://galaxy.citybreak.com/v5/api/content/category/{pointOfSaleId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId  |  The point of sales identifier.
Accept-Language | The language culture (e.g en-us)

## Point Of Interest

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v5/api/content/poi/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/content/poi/{pointOfSaleId}",
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

`GET https://galaxy.citybreak.com/v5/api/content/poi/{pointOfSalesId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId  |  The point of sales identifier.
Accept-Language | The language culture (e.g en-us)

## Languages

```shell
curl -X GET
--header 'apiKey: APIKEY132456789EWOK'  
--header 'Accept: application/json' 
'https://galaxy.citybreak.com/v5/api/content/language/{pointOfSaleId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/content/language/{pointOfSaleId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
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

`GET https://galaxy.citybreak.com/v5/api/content/language/{pointOfSaleId}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId  |  The point of sales identifier.
