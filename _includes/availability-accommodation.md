# Availability - Accommodation

> Availability


**Availability - Accommodation** calls provide information about the availability of accomodation products and (seperately) cabin products. These product types are split due to the nature of Cabin booking, typically set periods like Mon-Thurs, that produce different results for searches. Hotels, etc. return results based on the provided arrival and departure date. Cabins produce a "fuzzier" result, looking for matching periods for the requested dates within a margin of error. Both searches will return products with availability, including content, pricing groups with room information (Placements) and subproduct information (such as breakfasts or tickets to nearby attractions), as well as a Search ID with its Expiry. 

The **Search Id** can be used to retrieve prior, cached searches in a much shorter amount of time for both Accomodation Search and Cabin Scan if used before its Expiry. The object recalled by the search contains all the unfiltered information retrieved in the first search, so further or different filtering on content, etc. can be done in this call.

The **Search Id** and the **Booking Key** of each room product are used in the basket operations to add the product found to the <a href="https://visit.github.io/galaxy-docs/#Basket">Basket</a> 


**GET** and **POST** operations 

## Accommodation

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' -d '{
   "PointOfSalesId": {pointOfSalesId},
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
 }' 'https://galaxy.citybreak.com/v3/api/availability/accommodation'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation",
{
	method: "POST",
	headers: {
	    "ApiKey:" "APIKEY132456789EWOK",
	    "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
	   "PointOfSalesId": {pointOfSalesId},
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
    "PointOfSalesId": {pointOfSaleId},
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
    "OutputFilter": null
  },
  "Accommodations": [
    {
      "Id": "cbis:1136433",
      "Name": "Edelbrock Hotell 3",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=4014876",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=4014877",
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
            "Value": "Edelbrock Hotell 3"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Edelbrock Hotell"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Edelbrock Hotell!"
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
              "IncludedSubProducts": [],
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
              }
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
              "Name": "Dubbelrum ÖSD",
              "Content": {
                "PriceFrom": null,
                "Images": [],
                "Information": [
                  {
                    "Id": 99,
                    "Name": "Name",
                    "Value": "Dubbelrum ÖSD"
                  }
                ],
                "Categories": null,
                "Geos": null,
                "Pois": null,
                "Position": null
              },
              "IncludedSubProducts": [
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
              }
            }
          ],
          "BookingKey": "19-A"
        }
      ],
      "TotalResults": 2
    }
  ],
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh",
  "ExpirationDate": "2017-09-15T09:15:46.0619347Z",
  "TotalResults": 1
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as arrival and departure dates. 
The filter can also include <a href="https://visit.github.io/api-doc/#filter">content filtering</a>, such as only including those hotels associated with a particular CBIS category or that have 24 hr reception.
Content possibilities can be found in the <a href="https://visit.github.io/galaxy-docs/#content">Content Section</a> You can see a bare minimum verison of this search in the examples.
The Most important return values in this response are the **SearchId** and the **BookingKey** used in the <a href="https://visit.github.io/galaxy-docs/#basket">Basket</a>, also pay attention to the *ExpirationDate* of the SearchId

### HTTP Request

`POST https://galaxy.citybreak.com/availability/accommodation`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

## Get Previous Search

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' -d '{
  "Page": 1,
  "PageSize": 20,
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh"
}' 'https://galaxy.citybreak.com/v3/api/availability/accommodation/get'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation/get",
{
	method: "POST",
	headers: {
	   "ApiKey:" "APIKEY132456789EWOK",
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
    "PointOfSalesId": {pointOfSaleId},
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
      "Id": "cbis:1136433",
      "Name": "Edelbrock Hotell 3",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=4014876",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=4014877",
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
            "Value": "Edelbrock Hotell 3"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Edelbrock Hotell"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Edelbrock Hotell!"
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
              "IncludedSubProducts": [],
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
              "Name": "Dubbelrum ÖSD",
              "Content": {
                "PriceFrom": null,
                "Images": [],
                "Information": [
                  {
                    "Id": 99,
                    "Name": "Name",
                    "Value": "Dubbelrum ÖSD"
                  }
                ],
                "Categories": null,
                "Geos": null,
                "Pois": null,
                "Position": null
              },
              "IncludedSubProducts": [
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
              }
            }
          ],
          "BookingKey": "19-A"
        }
      ],
      "TotalResults": 2
    }
  ],
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh",
  "ExpirationDate": "2017-09-15T09:15:46.0619347Z",
  "TotalResults": 1
}
```

This is a **POST** request that requires a filter with a valid (non-expired) SearchId. The filter otherwise behaves the same as it would in the original <a href="https://visit.github.io/galaxy-docs/#accommodation19">Accommodation availability</a> search. You can see a bare minimum verison of this search in the examples.

### HTTP Request

`POST https://galaxy.citybreak.com/v3/api/availability/accommodation/get`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

## Calendar Search

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' -d '{
  "PointOfSalesId": {pointOfSaleId},
  "Start": "2018-11-09",
  "End": "2018-11-13",
  "Currency": "SEK"
}' 'https://galaxy.citybreak.com/v3/api/availability/accommodation/calendar'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/accommodation/calendar",
{
	method: "POST",
	headers: {
	   "ApiKey:" "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": {pointOfSaleId},
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
      "IsAvailable": true,
      "Groups": [
        {
          "Id": "ptg:1234567",
          "Name": "Visit Hotell",
          "Products": [
            {
              "Id": "pt:54321",
              "Name": "Double room",
              "Nights": 1
            },
            {
              "Id": "pt:54321",
              "Name": "Double room",
              "Nights": 2
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
              "Nights": 1
            }
          ]
        }
      ]
    },
    {
      "Date": "2018-11-10T00:00:00",
      "IsAvailable": false,
      "Groups": [
        {
          "Id": "ptg:1234567",
          "Name": "Visit Hotell",
          "Products": [
            {
              "Id": "pt:54321",
              "Name": "Double room",
              "Nights": 1
            }
          ]
        }
      ]
    },
    {
      "Date": "2018-11-11T00:00:00",
      "IsAvailable": false,
      "Groups": null
    },
    {
      "Date": "2018-11-12T00:00:00",
      "IsAvailable": false,
      "Groups": null
    },
    {
      "Date": "2018-11-13T00:00:00",
      "IsAvailable": false,
      "Groups": null
    },
  ],
  "CalendarContext": {
    "PointOfSalesId": {pointOfSalesId},
    "Start": "2018-11-09T00:00:00",
    "End": "2018-11-13T00:00:00",
    "Currency": "SEK",
    "ContentFilter": null
  }
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as the start and end dates of the calendar, the pointOfSalesId and the currency. 
As in other availability queries, the filter can also include a <a href="https://visit.github.io/api-doc/#filter">content filter</a>, such as only those hotels associated with a particular CBIS category or that have 24 hr reception. 
Content possibilities can be found in the <a href="https://visit.github.io/galaxy-docs/#content">Content Section</a> You can see a bare minimum verison of this search in the examples.
The return of this call is a set of days with an IsAvailable boolean value indicating any availability at all and (if there is availability) an entity called Groups which shows accommmodation options available on that day with the nested sub-products (think hotels with sub-products being hotel rooms) in the search period and the possible lengths of stay. This is useful for, say, quickly displaying days on which you can begin a stay and, once clicked, the minimum and maximum number of days you may stay within the search period.
 
### HTTP Request

`POST https://galaxy.citybreak.com/v3/api/availability/accommodation/calendar`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)