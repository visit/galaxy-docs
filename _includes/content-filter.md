# Content Filter

Content filters used in availability queries. All individual filters are optional, i.e. you can filter just on `Categories` and `Search`

<code class="center-column">
{
  "Geos": [],
  "Categories": [],
  "Pois": [],
  "Search": "",
  "Position": {},
  "Information": {},
  "Ids": []
}
</code>

## Categories, Geonodes, Pois

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
   ContentFilter{
    "Categories": [
		  123, 124
	  ],
	  "Geos": [
	  	123, 124
	   ],
	  "Pois": [
		123, 124
	  ]
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
    "ContentFilter"{
      "Categories": [
        123, 124
      ],
      "Geos": [
        123, 124
      ],
      "Pois": [
        123, 124
      ]
    }
	})  
});
```

Categories, Geonodes and Pois are list of integers. The example query can be translated to products (in category 123 **OR** 124) **AND** (in geonode 123 **OR** 124) **AND** (in poi 123 **OR** 124).

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
Categories | int[] | List of categories Ids.
Geos | int[] | List of geonodes Ids.
Pois | int[] | List of pois Ids.

## Search in Name

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
   ContentFilter{
    "Search":"My Hotel"
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
    "ContentFilter"{
      "Search":"My Hotel"
    }
	})  
});
```

Shorthand to search in products name.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
Search | string | String you are looking for, handles typos.

## Position

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
   ContentFilter{
    "Position": {
      "Latitude": 57.7089,
      "Longitude": 11.9746,
      "Distance": 10
	  }
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
    "ContentFilter"{
      "Position": {
        "Latitude": 57.7089,
        "Longitude": 11.9746,
        "Distance": 10
      }
    }
	})  
});
```

Filter products by their position. You need to supply a reference point and a `Distance` (radius in Km).

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
Latitude | double | Latitude of reference point.
Longitude | double | Longitude of reference point.
Distance | int | Distance from reference point (km).

## Ids

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
   ContentFilter{
      "Ids": [
        "cbis:12345", "ptg:987654"
      ]
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
    "ContentFilter"{
      "Ids": [
        "cbis:12345", "ptg:987654"
      ]
    }
	})  
});
```

Only return the products matching the ids supplied in `Ids`. These can be cbis product Id references ("cbis123456") or any unique product reference as stored in CBIS ("ptg:12345", "yourexternalref:12345")

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
Ids | string[] | The product Ids.

## Information

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
  ContentFilter{
      "Information": {
        "Operator": "AND",
        "Queries": [
          {
          "Id": 0,
          "Type": "Value",
          "Value": "string",
          "SubQuery": {
            "Operator": "OR",
            "Queries": [
              {
                "Id": 100059,
                "Type": "Value",
                "Value": "true"
              },
            "SubQuery": {}
            }
          }
        ]
      }
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
"ContentFilter":{
  "Information": {
    "Operator": "AND",
    "Queries": [
      {
        "Id": 110,
        "Type": "Has",
        "Value": null
      },
      {
        "Id": 100651,
        "Type": "Value",
        "Value": "false",
        "SubQuery":{
          "Operator": "AND",
          "Queries": [
            {
              "Id": 100666,
              "Type": "Value",
              "Value": "false"
            },
            {
              "Id": 100670,
              "Type": "Value",
              "Value": "true"
            }
          ]
        }
      }
    ]
  }
}
	})  
});
```

Filter products by the content of the Information they carry. You can filter on the existence of an attribute or on its content. Subqueries are a bit tricky but essentially allow you to mix AND and OR operators. For example the sample query asks for products where the following boolean logic is met `Has attribute 110 **OR** Attribute 100651 is false **OR** (100666 is false **AND** 100666 is true)`

### Operator

* AND
* OR

### MatchType

* Value (exact match, requires `Value`)
* Fuzzy (approx match, requires `Value`)
* Range (mathematical range, requires `Value`: \[1:10\], \]1;10\[, >3, <10 etc...)
* Has (has the attribute)
* Hasnt (has not the attribute)

### Information & SubQuery objects

Parameter | Type | Description
--------- | ---- | -----------
Operator | Operator | The operator to apply between the queries.
Queries | Query[] | A list of query.

### Query object

Parameter | Type | Description
--------- | ---- | -----------
Id | int | Attribute Id.
Type | MatchType | See above.
Value | string | The value.
SubQuery | SubQuery | See above.