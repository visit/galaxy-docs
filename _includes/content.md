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
-d '{
  "PointOfSalesId": 13723,
  "PageSize": 50,
  "Page": 0,
  "ContentFilter": {
    "Ids": [
      "cbis:1614826"
    ]
  }
}' 'https://galaxy.citybreak.com/v5/api/content/product'
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
    "PointOfSalesId": 13723,
    "PageSize": 50,
    "Page": 0,
    "ContentFilter": {
      "Ids": [
        "cbis:1614826"
      ]
    }
  })  
});
```

Example of response:

```json
{
  "Page": 0,
  "PageSize": 50,
  "TotalResults": 1,
  "Items": [
    {
      "ProductType": "Transport",
      "Id": "cbis:1614826",
      "Images": [
        {
          "Uri": "//images.citybreak.com/image.aspx?ImageId=4019784",
          "IsMain": false,
          "Name": null,
          "Copyright": null,
          "Description": null
        },
        {
          "Uri": "//images.citybreak.com/image.aspx?ImageId=4287044",
          "IsMain": true,
          "Name": null,
          "Copyright": null,
          "Description": null
        }
      ],
      "Information": [
        {
          "Id": 297,
          "Name": "Zoom level",
          "Value": "17"
        },
        {
          "Id": 910,
          "Name": "UrlName",
          "Value": "Nryfjord_Sightseeing_B2B__1614826"
        },
        {
          "Id": 145,
          "Name": "Phone number (Booking)",
          "Value": "57631400"
        },
        {
          "Id": 147,
          "Name": "Country code (Booking)",
          "Value": "+47"
        },
        {
          "Id": 99,
          "Name": "Name",
          "Value": "Nærøyfjord Sightseeing B2B "
        },
        {
          "Id": 101,
          "Name": "Introduction",
          "Value": "Experience the Aurland fjord and Nærøy fjord up close. We travel from Flåm to   Gudvangen and make sure you get back to the starting-point when you desire. "
        },
        {
          "Id": 102,
          "Name": "Description",
          "Value": "Experience the Aurlandsfjord and Nærøyfjord, which is on the UNESCO world heritage   list up close. \r\nThe route between Flåm and Gudvangen is one of the most popular fjord   areas in all of Norway! The spectacular Nærøyfjord is surrounding by steep mountains (up to   1400m high) and beautiful waterfalls. \r\n\r\nEnjoy the silence and nature up close from  one  of our sightseeing boats. \r\n\r\nChoose between many departures and assemble your  journey as  you please.  For our disabeld guests we recommend our Premium vessels with  universal design. \r\n\r\nOn board our boats we serve refreshments and light meals. "
        },
        {
          "Id": 402,
          "Name": "Currency",
          "Value": "NOK"
        },
        {
          "Id": 415,
          "Name": "Price description",
          "Value": "per person"
        },
        {
          "Id": 902,
          "Name": "Duration",
          "Value": "3-4 hours"
        },
        {
          "Id": 710,
          "Name": "Departure from",
          "Value": "Flåm & Gudvangen"
        },
        {
          "Id": 100017,
          "Name": "Summer",
          "Value": "False"
        },
        {
          "Id": 100588,
          "Name": "Winter",
          "Value": "False"
        },
        {
          "Id": 100738,
          "Name": "Fall",
          "Value": "False"
        },
        {
          "Id": 100739,
          "Name": "Spring",
          "Value": "False"
        },
        {
          "Id": 100939,
          "Name": "Monday",
          "Value": "False"
        },
        {
          "Id": 100587,
          "Name": "All year",
          "Value": "True"
        },
        {
          "Id": 102391,
          "Name": "No (bicycles not allowed)",
          "Value": "False"
        },
        {
          "Id": 100940,
          "Name": "Tuesday",
          "Value": "False"
        },
        {
          "Id": 100941,
          "Name": "Wednesday",
          "Value": "False"
        },
        {
          "Id": 100942,
          "Name": "Thursday",
          "Value": "False"
        },
        {
          "Id": 100943,
          "Name": "Friday",
          "Value": "False"
        },
        {
          "Id": 100944,
          "Name": "Saturday",
          "Value": "False"
        },
        {
          "Id": 100945,
          "Name": "Sunday",
          "Value": "False"
        },
        {
          "Id": 102390,
          "Name": "All days",
          "Value": "True"
        },
        {
          "Id": 102392,
          "Name": "Yes (bicycles allowed)",
          "Value": "False"
        },
        {
          "Id": 102393,
          "Name": "Everyone",
          "Value": "True"
        },
        {
          "Id": 102394,
          "Name": "Family",
          "Value": "False"
        },
        {
          "Id": 102395,
          "Name": "The adventurous",
          "Value": "False"
        },
        {
          "Id": 100847,
          "Name": "January",
          "Value": "True"
        },
        {
          "Id": 100848,
          "Name": "February",
          "Value": "True"
        },
        {
          "Id": 100849,
          "Name": "March",
          "Value": "True"
        },
        {
          "Id": 100850,
          "Name": "April",
          "Value": "True"
        },
        {
          "Id": 100851,
          "Name": "May",
          "Value": "True"
        },
        {
          "Id": 100852,
          "Name": "June",
          "Value": "True"
        },
        {
          "Id": 100853,
          "Name": "July",
          "Value": "True"
        },
        {
          "Id": 100854,
          "Name": "August",
          "Value": "True"
        },
        {
          "Id": 100855,
          "Name": "September",
          "Value": "True"
        },
        {
          "Id": 100856,
          "Name": "October",
          "Value": "True"
        },
        {
          "Id": 100857,
          "Name": "November",
          "Value": "True"
        },
        {
          "Id": 100858,
          "Name": "December",
          "Value": "True"
        }
      ],
      "Categories": [
        {
          "Id": 26397,
          "Path": "Aurland (Visit Flåm)"
        },
        {
          "Id": 26401,
          "Path": "To do"
        },
        {
          "Id": 26402,
          "Path": "Activities"
        },
        {
          "Id": 26403,
          "Path": "Fjord Cruise"
        },
        {
          "Id": 26397,
          "Path": "Aurland (Visit Flåm)"
        },
        {
          "Id": 26401,
          "Path": "To do"
        },
        {
          "Id": 26402,
          "Path": "Activities"
        }
      ],
      "Geos": [
        {
          "Id": 76664,
          "Path": "[Aurland (Visit Flåm)]"
        },
        {
          "Id": 108308,
          "Path": "Norway"
        },
        {
          "Id": 80944,
          "Path": "Flåm"
        }
      ],
      "Pois": [],
      "Position": {
        "Latitude": 60.8628231038964,
        "Longitude": 7.11472034454346
      }
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
