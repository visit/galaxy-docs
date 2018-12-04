
# Fuzzy Accommodation Search

The fuzzy accommodation search will look for available accommodation options in the vicinity of the requested Arrival/Departure of the stay definition. The result will give you options that match or partially match the stay definition. A score will tell how good of a match it was. You can use the related methods to navigate in the search result until it is resolved into a bookable match. Once you have found the accommodation product you are looking for (or the end user has selected it) you can put that selection and required stay dates in the basket.

## How to add a result to basket

### Call Scan
First you call the Scan method to get perform a search. You will get a partial listing back describing the first set of results. The `SearchId` will be used in all other methods
to refer back to the original search you made.  The scan operation will examine dates around the stay (-10 days before arrival and +10  days after the selected departure), and give you bookkeys to pass to the next methods.

### Page through the result
By using the Get method you will be able to page through the result.

### Get arrival dates in search span
Once you get a result you like and would like to investigate further you can get more details of the possible stays with that result by calling *arrivaldates* with a `bookKey` obtained with the *scan* or get methods. That will give you all valid arrival dates available in scan sector that was  used.

### Get departure dates 
By calling the `departuredates` with a `bookKey` obtained with the <a href="https://visit.github.io/galaxy-docs/#scan">scan</a> method, given an arrival date you will get all valid departures from that date.

### List bookable alternatives
By calling *bookablealternatives* you will get back actual bookable items between a specified arrival and departure. You will get a list of items back. Since an accommodation product may be sold under certain conditions, you may get more than one back. Each describing a price and the conditions under it will be sold. Included subproducts can differ between the items for instance.

### Add to basket
Once you have a bookable alternative you can add it to the basket by calling *PUT api/basket/add/cabin/\{basketId\}/\{searchId\}/\{bookKey\}*


## Scan 

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
  "PointOfSalesId": 0,
  "Currency": "EUR",
  "PageSize": 20,
  "Stay": {
    "ArrivalDaysMask": 0x7F, 
    "DepartureDayMask": 0x7F,
    "MinStayLength": 3,
    "MaxStayLength": 5,
    "Arrival": "2018-12-04",
    "Departure": "2018-12-08"
  },
  "PersonConfiguration": {
    "Adults": 2,
    "ChildrenAges": [
    ]
  },
  "OutputFilter":{
    "Attributes":[
      99
    ]
  }
  "Sort": {
    "Order": "Asc",
    "Field": "Score"
    } 
}' 'http://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/scan'
```

```javascript
var r = fetch("http://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/scan",
{
	method: "POST",
	headers: {
	    "ApiKey:" "APIKEY132456789EWOK",
	    "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 0,
    "Currency": "SEK",
    "PageSize": 20,
    "Stay": {
      "ArrivalDaysMask": 0x7F,
      "DepartureDayMask": 0x7F, 
      "MinStayLength": 3,
      "MaxStayLength": 5,
      "Arrival": "2018-12-04",
      "Departure": "2018-12-08"
    },
    "PersonConfiguration": {
      "Adults": 2,
      "ChildrenAges": [
      ]
    },
    "Sort": {
      "Order": "Asc",
      "Field": "Score"
    }
  })  
});
```

> Example of response:

```json
{
  "SearchId": "1234abcd-a1b2-1234-a10f-abcd1234abcd",
  "TotalResults": 2,
  "Accommodations": [
    {
      "Id": "cbis:12345",
      "Name": "First hotel",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=123456",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 99,
            "Name": "Namn",
            "Value": "First hotel"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": {
          "Latitude": 60.12345,
          "Longitude": 18.00000
        }
      },
      "Products": [
        {
          "Id": "pt:12345",
          "BookingKey": "2-C",
          "Name": "Standard Dubbelrum",
          "Content": {
            "PriceFrom": 0,
            "Images": [],
            "Information": [
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
          },
          "Score": 100,
          "ExampleArrival": "2018-12-04T00:00:00+01:00",
          "ExampleDeparture": "2018-12-08T00:00:00+01:00",
          "Extrabeds": 1,
          "MaxPopluationForAnyItem": 3,
          "MaxPopulation": 2,
          "OriginalPrice": 300,
          "Price": 300
        },
        {
          "Id": "pt:23456",
          "BookingKey": "2-C",
          "Name": "Trippelrum",
          "Content": {
            "PriceFrom": 0,
            "Images": [],
            "Information": [
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
          },
          "Score": 65,
          "ExampleArrival": "2018-12-04T00:00:00+01:00",
          "ExampleDeparture": "2018-12-07T00:00:00+01:00",
          "Extrabeds": 0,
          "MaxPopluationForAnyItem": 3,
          "MaxPopulation": 3,
          "OriginalPrice": 250,
          "Price": 250
        },
        {
          "Id": "pt:34567",
          "BookingKey": "2-C",
          "Name": "Superior Dubbelrum",
          "Content": {
            "PriceFrom": 0,
            "Images": [],
            "Information": [
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
          },
          "Score": 65,
          "ExampleArrival": "2018-12-04T00:00:00+01:00",
          "ExampleDeparture": "2018-12-07T00:00:00+01:00",
          "Extrabeds": 1,
          "MaxPopluationForAnyItem": 3,
          "MaxPopulation": 2,
          "OriginalPrice": 280,
          "Price": 280
        }
      ]
    }
  ],
  "SearchContext": {
    "Arrival": "2018-12-04T00:00:00+01:00",
    "Departure": "2018-12-08T00:00:00+01:00",
    "OutputFilter": {
      "Attributes": [
        99
      ],
      "Categories": false,
      "Geos": false,
      "Pois": false,
      "Position": false
    },
    "ContentFilter": {
      "Geos": [],
      "Categories": [],
      "Pois": [],
      "Search": null,
      "Position": null,
      "Information": null,
      "Ids": []
    },
    "PageSize": 20,
    "Page": 0,
    "PersonConfiguration": {
      "Adults": 1,
      "ChildrenAges": []
    },
    "Currency": "EUR",
    "ArrivalDayMask": 127,
    "DepartureDayMask": 127,
    "MinStayLength": 3,
    "MaxStayLength": 5,
    "Sort": {
      "Order": "Desc",
      "Field": "Score"
    }
  },
  "ExpirationDate": "2018-11-20T12:00:00.1000000+01:00"
}
```

Use this method first to get a `BookKey` to be able to proceed with all other 
operations. 

### Search parameters
All parameters are submitted through an instance of the CabinSearchFilter object as described below.

|Parameter|Description|
|------|-----|
PointOfSalesId|The point of sales that should be used. It defines the assortment that could be searched.|
Currency|The currency the basket search should deliver results for. It must match the currency your basket is in.
PageSize|The number of results in the return object. It may not exceed 50 and suggested is between 10 and 20.
Page|The page you would like to start with. Normally 0, it will give you the first page with the best matches
Stay|The Stay object describes what types of stay results you would like to get.
Stay.ArrivalDayMask|The arrival day mask, see DayMask below.
Stay.DepartureDayMask|The departure day mask, see DayMask below.
Stay.MinStayLength|The minimum length of stay you require.
Stay.MaxStayLength|The maximum length of stay you require.
Stay.Arrival|The suggested arrival date.
Stay.Departure|The suggested departure date.

### Using the Stay object
The `arrival` and `departure` makes up a sweet spot span where you would like to arrive. The search is performed with the focus on that area. However you can get results that partially matches that span.

The `Score` property will tell how good of a match a specific result was. It will also give you the best price for the specified stay that the item used to 
calculate the score. 
The example properties on that object will tell which ones it was.

Use the `arrival`/`departure` day mask to create queries to match like short week, 
weekends and such.
For instance, use 0x18 to create results arriving on Thursday or Friday and use departure
mask 0x61 to specify acceptable departures on Saturday, Sunday or Monday. 
That could be your weekend day filter.

Use the `MinStayLength`/`MaxStayLength` stay to specify an acceptable length of you stay. 
7/7 will give you exactly seven days of stay.
2/3 will restrict the stay to 2 or 3 days. 
That could be used in conjunction with the week days filter.
1/7 will give you results where you could stay anywhere between 1 or 7 days - likely to be an expensive and possibly not helpful query

Keep in mind that this is only used to give you relevant stay dates as the result.
You can use the get arrival dates and departure dates when you examine a specified 
result to create a bookable result that does not necessarily matches your 
original constraints. 


#### Day mask
A bit mask describing which days that are valid for arriving at or depart at. The field is an integer but can also be represented in hex. 

|Hex|Day|Bin
|-----|-----|-----|
0x01|Monday|(0000001)
0x02|Tuesday|(0000010)
0x04|Wednesday|(0000100)
0x08|Thursday|(0001000)
0x10|Friday|(0010000)
0x20|Saturday|(0100000)
0x40|Sunday|(1000000)

##### Examples
|Mask|Meaning|
|-----|------|
0x7F|Any day, this is the default if 0 is submitted.
0x18|Thursday or Friday.
0xF|Monday, Tuesday, Wednesday, Thursday or Friday.

#### Sort definition
The sort definition is used to order the paged results you get. 

|Order|Meaning|
|------|------|
Asc|Ascending - The item with the lowest field value first. Suggested when sorting by Price.
Desc|Descending - The item the highest field value first. Suggested when sorting by Score.

|Field|Meaning|
|------|------|
Name|Sort by the name of the Cabin
Price|Sort by example price
Random|Sort by a random order.
Score|Sort by the relevance of the example stay.

Suggested sort order is by `Score`/`Descending`. 
That will give you the most relevant items first. 
<aside class="notice">Please note that price may give some unintended side effects when using
`MaxStayLength`/`MinStayLength` and `ArrivalDayMask`/`DepartureDayMask` filter.
The items may not compare well to each other since one item may have produced 
a result that is shorter than another (hence a different price) or 
using `ArrivalDayMask`/`DepartureDayMask`.</aside>
The price may differ heavily if you are in a high season week and low season week. 
Ordering by `Price` is therefore not necessarily a good sorting for listing 
relevant results. 

### ContentFilter
The content filter specifies that the search result should be narrowed to certain
results that only matches that filter. See Availability search for specification.

### ContentOutputFilter
The output filter describes which content that should be included with the item.
See the availability search for specifications.

This is **POST** request that requires a filter. You can see a bare minimum version of this search in the examples.

### HTTP Request

`POST https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/scan`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<div class="center-column"></div>
```
{
  "PointOfSalesId": 0, //int - Mandatory 
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "PageSize": 0, //int Mandatory
  "Stay": { // Mandatory
    "ArrivalDaysMask": 0, //int - Optional - use only rightmost seven bits, defaults to 127 (all days)
    "DepartureDayMask": 0, //int - Optional - use only rightmost seven bits, defaults to 127 (all days)
    "MinStayLength": 0, // int - Mandatory
    "MaxStayLength": 0, // int - Mandatory
    "Arrival": "2018-11-23T15:23:15.087Z", //DateTime - Mandatory, conforms to ISO 8601
    "Departure": "2018-11-23T15:23:15.088Z", //DateTime - Mandatory, conforms to ISO 8601
  },
  //List of configurations for guest numbers. Each item represents a "room". 
  //Cannot be empty, must represent at least one guest
  "PersonConfigurations": [
    {
      "Adults": 0, //int - represents number of adults
      "ChildrenAges": [ //List of ints - each int represents the age of a child guest
        0
      ]
    }
  ],
  "ContentFilter": { // Optional - See the ContentFilter section
  },
  "OutputFilter": { // Optional -  See the OutputFilter section
  },
  "Sort": { // Optional - default sort is price ascending
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string" //string - Mandatory if parent included - Price, Name, Score, Random
  }
}
```


## Get
```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
    "Page": 1, // Zero indexed so this is the second page
    "PageSize": 10,
    "Sort": {
      "Order": "Desc",
      "Field": "Score"
    },
    "SearchId": "1234abcd-a1b2-1234-a10f-abcd1234abcd",
    "ContentOutputFilter": {
      "Attributes": [
          99
      ],
      "Categories": false,
      "Geos": false,
      "Pois": false,
      "Position": false
    }
}' 'https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/get'
```
```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/get",
{
	method: "POST",
	headers: {
	    "ApiKey:" "APIKEY132456789EWOK",
	    "Accept": "application/json",
		  "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
  "Page": 1, // Zero indexed so this is the second page
  "PageSize": 10,
  "Sort": {
    "Order": "Desc",
    "Field": "Score"
  },
  "SearchId": "1234abcd-a1b2-1234-a10f-abcd1234abcd",
  "ContentOutputFilter": {
    "Attributes": [
        99
    ],
    "Categories": false,
    "Geos": false,
    "Pois": false,
    "Position": false
  }
  })  
});
```

This method is used to get a different page of the scan result as represented by the searchId you find in the initial scan. Each searchId has an expiry but this is not a guarantee of availability on results from previous pages.

### HTTP Request

`POST https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/get`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<div class="center-column"></div>
```
{
  "Page":1, //int mandatory - the pager is 0-indexed so 1 is the second page
  "PageSize": 0, //int Mandatory
  "Sort": { // Optional
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string" //string - Mandatory if parent included - Price, Name, Random
  },
  "SearchId":"string", //string - Mandatory - the search Id of a still valid accommodation availability search
  "OutputFilter": { // Optional -  See the OutputFilter section
  }
}
```

## Arrival dates
```shell
curl -X GET 
--header 'Accept: text/plain' 
--header 'apiKey:  APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/arrivaldates?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&firstArrival=2018-12-03&lastArrival=2018-12-05&personConfig.adults=2'

```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/arrivaldates?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&firstArrival=2018-12-03&lastArrival=2018-12-05&personConfig.adults=2",
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
    "2018-12-03T00:00:00+01:00",
    "2018-12-04T00:00:00+01:00"
]
```
Get a set of valid arrival dates for a specified item based on your scan.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/arrivaldates`


### Query Parameters

Parameter | Description
--------- | -----------
searchId  | From the `result`
bookKey | From the `result.Result[n].BookKey`
firstArrival | First acceptable date for the result.
lastArrival | Last acceptable date for the result.
personConfig.adults | Number of adults (usually be same as scan)
personConfig.childrenAges | Ages of children  (usually be same as scan)

## Departure dates

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey:  APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/departuredates?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&arrival=2018-12-03&personConfig.adults=2'

```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/departuredates?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&arrival=2018-12-03&personConfig.adults=2",
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
  "2018-12-04T00:00:00+01:00",
  "2018-12-05T00:00:00+01:00",
  "2018-12-06T00:00:00+01:00",
  "2018-12-07T00:00:00+01:00",
  "2018-12-08T00:00:00+01:00",
  "2018-12-09T00:00:00+01:00",
  "2018-12-10T00:00:00+01:00",
  "2018-12-11T00:00:00+01:00",
  "2018-12-12T00:00:00+01:00",
  "2018-12-13T00:00:00+01:00",
  "2018-12-14T00:00:00+01:00",
  "2018-12-15T00:00:00+01:00",
  "2018-12-16T00:00:00+01:00",
  "2018-12-17T00:00:00+01:00"
]
```
Get a set of valid departure dates for the specified item given the arrival date.
### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/departuredates`

### Query Parameters

Parameter | Description
--------- | -----------
searchId  | From the `result`
bookKey | From the `result.Result[n].BookKey`
arrival | The specified arrival date from which you would like valid departure dates.
personConfig.adults | Number of adults (usually be same as scan)
personConfig.childrenAges | Ages of children  (usually be same as scan)


## Detailed Departure Info

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey:  APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/alldepartures?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&arrival=2018-12-03&personConfig.adults=2'

```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/alldepartures?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&arrival=2018-12-03&personConfig.adults=2",
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
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "1.00:00:00",
    "Price": 60,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "2.00:00:00",
    "Price": 120,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "3.00:00:00",
    "Price": 180,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "4.00:00:00",
    "Price": 240,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "5.00:00:00",
    "Price": 500,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "6.00:00:00",
    "Price": 600,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "7.00:00:00",
    "Price": 700,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "8.00:00:00",
    "Price": 800,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "9.00:00:00",
    "Price": 900,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "10.00:00:00",
    "Price": 1000,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "11.00:00:00",
    "Price": 1100,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "12.00:00:00",
    "Price": 1200,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "13.00:00:00",
    "Price": 1300,
    "OriginalPrice": null
  },
  {
    "Arrival": "2018-12-03T00:00:00+01:00",
    "Stay": "14.00:00:00",
    "Price": 1400,
    "OriginalPrice": null
  }
]
```
Similar to the departure dates query, this call will return a more detailed list of departure information, with stay time from your requested arrival date and the lowest price of the placement.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/alldepartures`

### Query Parameters

Parameter | Description
--------- | -----------
searchId  | From the `result`
bookKey | From the `result.Result[n].BookKey`
arrival | The specified arrival date from which you would like valid departure dates.
personConfig.adults | Number of adults (usually be same as scan)
personConfig.childrenAges | Ages of children  (usually be same as scan)

## Get bookable alternatives

```shell
curl -X GET --header 'Accept: application/json' --header 'apiKey:  APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/bookablealternatives?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&arrival=2018-12-03&personConfig.adults=2'

```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/bookablealternatives?searchId=1234abcd-a1b2-1234-a10f-abcd1234abcd&bookKey=2-C&arrival=2018-12-03&personConfig.adults=2",
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
    "BookId": 3,
    "DiscountInformation": null,
    "Arrival": "2018-12-04T00:00:00+01:00",
    "Departure": "2018-12-07T00:00:00+01:00",
    "Subproducts": [
      {
        "Name": "Frukost",
        "Currency": "EUR",
        "Description": null,
        "IncludedInPrice": true,
        "PayOnSite": false,
        "Price": 0
      }
    ],
    "OriginalPrice": null,
    "Price": 180,
    "RateInformation": {
      "Name": null,
      "CancellationLatest": null,
      "Terms": null
    }
  },
  {
    "BookId": 4,
    "DiscountInformation": null,
    "Arrival": "2018-12-04T00:00:00+01:00",
    "Departure": "2018-12-07T00:00:00+01:00",
    "Subproducts": [
      {
        "Name": "Frukost",
        "Currency": "EUR",
        "Description": null,
        "IncludedInPrice": true,
        "PayOnSite": false,
        "Price": 0
      }
    ],
    "OriginalPrice": null,
    "Price": 300,
    "RateInformation": {
      "Name": null,
      "CancellationLatest": "2018-06-10T02:00:00+02:00",
      "Terms": null
    }
  }
]
```

This call returns a list of valid alternatives to book. Use the `BookId` (different to the `bookKey`) when referring to this specific result when adding it to the <a href="https://visit.github.io/galaxy-docs/#add-fuzzy-booking-item">fuzzy search basket</a>.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/availability/accommodation/fuzzy/bookablealternatives`

### Query Parameters

Parameter | Description
--------- | -----------
searchId  | From the `result`
bookKey | From the `result.Result[n].BookKey`
arrival | The specified arrival date
departure | The specified departure date
personConfig.adults | Number of adults (usually be same as scan)
personConfig.childrenAges | Ages of children  (usually be same as scan)
