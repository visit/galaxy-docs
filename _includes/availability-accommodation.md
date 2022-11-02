# Availability - Placement Accommodation

**Availability - Placement Accommodation** calls provide information about the availability of any type of accommodation products. Both searches (normal and fuzzy) will return products with availability, including content, pricing groups with room information (Placements) and subproduct information (such as breakfasts or tickets to nearby attractions), as well as a Search ID with its Expiry. This search differs from the default <a href="#availability---noplacementaccommodation">accommodation</a> availability search in that it does automatic placement of persons into rooms. That means if you send two person configurations: one with 1 adult and one with 2 adults, you will get a list of room combinations priced and bookable as a whole.

The `SearchId` can be used to retrieve prior, cached searches in a much shorter amount of time if used before its Expiry. The object recalled by the search contains all the unfiltered information retrieved in the first search, so further or different filtering on content, etc. can be done in this call.

The `SearchId` and the `BookingKey` of each room product are used in the basket operations to add the product found to the <a href="#add-placement-accommodation-booking-item">Basket</a> 


**GET** and **POST** operations 

## Placement Accommodation

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
   ]
 }' 'https://galaxy.citybreak.com/v5/api/availability/accommodation/placement'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/accommodation/placement",
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
	   ]
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
    "Page": 0,
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
    "OutputFilter": null,
    "PromoCode": null,
    "OffersOnly": false,
    "OfferIds": []
  },
  "Accommodations": [
    {
      "Id": "cbis:12345",
      "Name": "BookVisit Hotel",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=10101010",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=1010101010",
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
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Leading e-commerce platform for the DMO and individual hotels in the Nordics."
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "The absolute Leading e-commerce platform for the DMO and individual hotels in the Nordics!"
          },
          {
            "Id": 100038,
            "Name": "Elevator",
            "Value": "False"
          },
          {
            "Id": 100163,
            "Name": "Reception",
            "Value": "False"
          }
        ],
        "Categories": null,
        "Geos": [],
        "Pois": [],
        "Position": null
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
              "Name": "Dubbelrum med extra säng",
              "Content": {
                "PriceFrom": null,
                "Images": [],
                "Information": [
                  {
                    "Id": 99,
                    "Name": "Name",
                    "Value": "Dubbelrum med extra säng"
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
                  0
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
              },
              "PromoCodeDescription": null,
              "PriorityAgreement": false,
              "Offer": null
            }
          ],
          "BookingKey": "18-A"
        },
        {
          "Price": {
            "Price": 500,
            "TotalPersons": 2,
            "Currency": "SEK",
            "DateStart": "2017-10-14T00:00:00Z",
            "DateEnd": "2017-10-15T00:00:00Z"
          },
          "Placements": [
            {
              "Name": "Dubbelrum",
              "Content": {
                "PriceFrom": null,
                "Images": [],
                "Information": [
                  {
                    "Id": 99,
                    "Name": "Name",
                    "Value": "Dubbelrum"
                  }
                ],
                "Categories": null,
                "Geos": null,
                "Pois": null,
                "Position": null
              },
              "IncludedAddons": [
                {
                  "Name": "Trädgårdstomte",
                  "Content": {
                    "PriceFrom": null,
                    "Images": [],
                    "Information": [
                      {
                        "Id": 99,
                        "Name": "Name",
                        "Value": "Trädgårdstomte"
                      }
                    ],
                    "Categories": null,
                    "Geos": null,
                    "Pois": null,
                    "Position": null
                  },
                  "Price": 150,
                  "Amount": 1,
                  "Currency": "SEK",
                  "PriceIncluded": false,
                  "IsExtraBed": false,
                  "PayOnSite": false
                }
              ],
              "MaxPopopulation": 3,
              "MinPopulation": 1,
              "ExtraBeds": 1,
              "PersonConfiguration": {
                "Adults": 1,
                "ChildrenAges": [
                  0
                ]
              },
              "PricePeriods": [
                {
                  "DateStart": "2017-10-14T00:00:00",
                  "DateEnd": "2017-10-15T00:00:00",
                  "AdultPrice": 250,
                  "ChildPrice": 100,
                  "TotalPrice": 350,
                  "Currency": "SEK"
                }
              ],
              "BookingConditions": {
                "Name": null,
                "Terms": null
              },
              "PromoCodeDescription": null,
              "PriorityAgreement": false,
              "Offer": null
            }
          ],
          "BookingKey": "19-A"
        }
      ],
      "TotalResults": 2
    }
  ],
  "PromoCodeStatus": "None",
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh",
  "ExpirationDate": "2017-09-15T09:15:46.0619347Z",
  "TotalResults": 1,
  "Operations": [
    {
      "System": "ExternalSystem",
      "Account": "ExternalAccount",
      "Action": "Search",
      "Duration": "00:00:01",
      "Success": true,
      "ErrorMessage": null
    }
  ]
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as arrival and departure dates. 
The filter can also include content filtering, such as only including those hotels associated with a particular CBIS category or that have 24 hr reception.
Content filtering possibilities can be found in the <a href="#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The Most important return values in this response are the `SearchId` and the `BookingKey` used in the <a href="#add-placement-accommodation-booking-item">Basket</a>, also pay attention to the `ExpirationDate` of the `SearchId`

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/accommodation/placement`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 0, //int - Mandatory 
  "Arrival": "2018-11-23T15:23:15.087Z", //DateTime - Mandatory
  "Departure": "2018-11-23T15:23:15.088Z", //DateTime - Mandatory
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "PageSize": 0, //int - Mandatory
  "Sort": { // Optional - defaults to Price Ascending
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string" //string - Mandatory if parent included - PriorityAgreement, Price, Name, Random
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
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a>
  },
  "OutputFilter": { // Optional -  See <a href="#output-filter">OutputFilter</a>
  },
  "PromoCode": "string", // string - Optional
  "OffersOnly": true, // bool - Optional - whether to return results with offers only
  "OfferIds": [ // Optional - list of offers to filter results with
    "string" // string - Mandatory if parent included
  ]
}
</code>

### Sort definition
The sort definition is used to order the paged results you get. 

|Order|Meaning|
|------|------|
Asc|Ascending - The item with the lowest field value first.
Desc|Descending - The item the highest field value first.

|Field|Meaning|
|------|------|
PriorityAgreement|Sort by priority agreement.
Name|Sort by name.
Price|Sort by price.
Random|Sort by a random order.

## Get Previous Search

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
  "Page": 1,
  "PageSize": 20,
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh"
}' 'https://galaxy.citybreak.com/v5/api/availability/accommodation/placement/get'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/accommodation/placement/get",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "Page": 1,
    "PageSize": 20,
    "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh"
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
    "OutputFilter": null,
    "PromoCode": null,
    "OffersOnly": false,
    "OfferIds": []
  },
  "Accommodations": [
    {
      "Id": "cbis:12345",
      "Name": "BookVisit Hotel",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=10101010",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=10101010",
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
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Leading e-commerce platform for the DMO and individual hotels in the Nordics."
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "The absolute Leading e-commerce platform for the DMO and individual hotels in the Nordics!"
          },
          {
            "Id": 100038,
            "Name": "Elevator",
            "Value": "False"
          },
          {
            "Id": 100163,
            "Name": "Reception",
            "Value": "False"
          }
        ],
        "Categories": null,
        "Geos": [],
        "Pois": [],
        "Position": null
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
              "Name": "Dubbelrum med extra säng",
              "Content": {
                "PriceFrom": null,
                "Images": [],
                "Information": [
                  {
                    "Id": 99,
                    "Name": "Name",
                    "Value": "Dubbelrum med extra säng"
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
              },
              "PromoCodeDescription": null,
              "PriorityAgreement": false,
              "Offer": null
            }
          ],
          "BookingKey": "18-A"
        },
        {
          "Price": {
            "Price": 500,
            "TotalPersons": 2,
            "Currency": "SEK",
            "DateStart": "2017-10-14T00:00:00Z",
            "DateEnd": "2017-10-15T00:00:00Z"
          },
          "Placements": [
            {
              "Name": "Dubbelrum",
              "Content": {
                "PriceFrom": null,
                "Images": [],
                "Information": [
                  {
                    "Id": 99,
                    "Name": "Name",
                    "Value": "Dubbelrum"
                  }
                ],
                "Categories": null,
                "Geos": null,
                "Pois": null,
                "Position": null
              },
              "IncludedAddons": [
                {
                  "Name": "Trädgårdstomte",
                  "Content": {
                    "PriceFrom": null,
                    "Images": [],
                    "Information": [
                      {
                        "Id": 99,
                        "Name": "Name",
                        "Value": "Trädgårdstomte"
                      }
                    ],
                    "Categories": null,
                    "Geos": null,
                    "Pois": null,
                    "Position": null
                  },
                  "Price": 150,
                  "Amount": 1,
                  "Currency": "SEK",
                  "PriceIncluded": false,
                  "IsExtraBed": false,
                  "PayOnSite": false
                }
              ],
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
                  "AdultPrice": 250,
                  "ChildPrice": 100,
                  "TotalPrice": 350,
                  "Currency": "SEK"
                }
              ],
              "BookingConditions": {
                "Name": null,
                "Terms": null
              },
              "PromoCodeDescription": null,
              "PriorityAgreement": false,
              "Offer": null
            }
          ],
          "BookingKey": "19-A"
        }
      ],
      "TotalResults": 2
    }
  ],
  "PromoCodeStatus": "None",
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh",
  "ExpirationDate": "2017-09-15T09:15:46.0619347Z",
  "TotalResults": 1,
  "Operations": [
    {
      "System": "ExternalSystem",
      "Account": "ExternalAccount",
      "Action": "Search",
      "Duration": "00:00:01",
      "Success": true,
      "ErrorMessage": null
    }
  ]
}
```

This is a **POST** request that requires a filter with a valid (non-expired) SearchId. The filter otherwise has the same constraints as in the original <a href="#availability---accommodation">Accommodation availability</a> search. You can see a bare minimum version of this search in the examples.

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/accommodation/placement/get`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "Page":1, //int mandatory - the pager is 0-indexed so 1 is the second page
  "PageSize": 0, //int Mandatory
  "Sort": { // Optional
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string" //string - Mandatory if parent included - Price, Name, Random
  },
  //string - Mandatory - the search Id of a still valid accommodation availability search
  "SearchId":"string", 
  "OutputFilter": { // Optional -  See <a href="#output-filter">OutputFilter</a>
  }
}
</code>

## Calendar Search

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
  "PointOfSalesId": 0,
  "Start": "2018-11-09",
  "End": "2018-11-13",
  "Currency": "SEK"
}' 'https://galaxy.citybreak.com/v5/api/availability/accommodation/calendar'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/accommodation/calendar",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 0,
    "Start": "2018-11-09",
    "End": "2018-11-13",
    "Currency": "SEK"
  })  
});
```

> Example of response:

```json
{
  "Calendar": [
    {
      "Date": "2018-11-09T00:00:00",
      "Groups": [
        {
          "Id": "ptg:987654",
          "Name": "Visit Hotell",
          "Products": [
            {
              "Id": "pt:54321",
              "Name": "Single room",
	      "PriceFrom": 100,
              "StayLenghts": [1, 2]
            },
            {
              "Id": "pt:54322",
              "Name": "Double room",
	      "PriceFrom": 100,
              "StayLenghts": [1, 2]
            }
          ]
        },
        {
          "Id": "ptg:2345678",
          "Name": "Citybreak Hotell",
          "Products": [
            {
              "Id": "pt:65432",
              "Name": "Double room",
	      "PriceFrom": null,
              "StayLenghts": [7, 14]
            }
          ]
        }
      ]
    },
    {
      "Date": "2018-11-10T00:00:00",
      "Groups": [
        {
          "Id": "ptg:1234567",
          "Name": "Visit Hotell",
          "Products": [
            {
              "Id": "pt:54321",
              "Name": "Double room",
	      "PriceFrom": 100,
              "StayLenghts": [1, 2]
            }
          ]
        }
      ]
    }
  ],
  "PromoCodeStatus": "None",
  "CalendarContext": {
    "PointOfSalesId": 0,
    "Start": "2018-11-09T00:00:00",
    "End": "2018-11-13T00:00:00",
    "Currency": "SEK",
    "ContentFilter": null,
    "PromoCode": null
  },
  "Operations": [
    {
      "System": "ExternalSystem",
      "Account": "ExternalAccount",
      "Action": "Search",
      "Duration": "00:00:01",
      "Success": true,
      "ErrorMessage": null
    }
  ]
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as the start and end dates of the calendar, the pointOfSalesId and the currency. 
As in other availability queries, the filter can also include a content filter, such as only those hotels associated with a particular CBIS category or that have 24 hr reception. 
Content possibilities can be found in the <a href="#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The return of this call is a set of availble dates (if there is availability) an entity called Groups which shows accommodation options available on that day with the nested sub-products (think hotels with sub-products being hotel rooms) in the search period and the possible lengths of stay. This is useful for, say, quickly displaying days on which you can begin a stay and, once clicked, the minimum and maximum number of days you may stay within the search period. There can also be a from price available, if supported by the external system.
 
### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/accommodation/calendar`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 0, //int - Mandatory 
  "Start": "2018-11-23", //DateTime - Mandatory, conforms to ISO 8601
  "End": "2018-11-23", //DateTime - Mandatory, conforms to ISO 8601
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a>
  },
  "PromoCode": "string", // string - Optional
  "OffersOnly": true, // bool - Optional - whether to return results with offers only
  "OfferIds": [ // Optional - list of offers to filter results with
    "string" // string - Mandatory if parent included
  ]
}
</code>
