# Availability

> Availability

<aside class="warning">.NB: Cabin Search and Retrieving Queries calls are in development development and may not be working.</aside>
**Availability** calls provide information about the availability of accomodation products and (seperately) cabin products. These product types are split due to the nature of Cabin booking, typically set periods like Mon-Thurs, that produce different results for searches. Hotels, etc. return results based on the provided arrival and departure date. Cabins produce a "fuzzier" result, looking for matching periods for the requested dates within a margin of error. Both searches will return products with availability, including content, pricing groups with room information (Placements) and subproduct information (such as breakfasts or tickets to nearby attractions), as well as a Search ID with its Expiry. 

The **Search Id** can be used to retrieve prior, cached searches in a much shorter amount of time for both Accomodation Search and Cabin Scan if used before its Expiry. The object recalled by the search contains all the unfiltered information retrieved in the first search, so further or different filtering on content, etc. can be done in this call.

The **Search Id** and the **Booking Key** of each room product are used in the basket operations to add the product found to the <a href="https://visit.github.io/galaxy-docs/#Basket">Basket</a> 

The Cabin Search has additional functionality - the **GET** calls - 

**GET** and **POST** operations 
<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the **{pointOfSalesId}**</aside>

## Accommodation

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' -d '{
   "PointOfSalesId": {pointOfSalesId},
   "Arrival": "2017-10-14T12:27:58.851Z",
   "Departure": "2017-10-15T12:27:58.851Z",
   "Currency": "SEK",
   "PageSize": 20,
   "Page": 0,
   "PersonConfigurations": [
     {
       "Adults": 1,
       "ChildrenAges": [
         0
       ] 
     }
   ]
 }' 'https://galaxy.test.citybreak.com/api/availability/accommodation'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/availability/accommodation",
{
	method: "POST",
	headers: {
	    "ApiKey:" "APIKEY132456789EWOK",
	    "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
	   "PointOfSalesId": {pointOfSalesId},
	   "Arrival": "2017-10-14T12:27:58.851Z",
	   "Departure": "2017-10-15T12:27:58.851Z",
	   "Currency": "SEK",
	   "PageSize": 20,
	   "Page": 0,
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
      "Id": 1136433,
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
  "SearchId": "899fe054-3bb4-4ff8-b577-ba716b0b3317",
  "ExpirationDate": "2017-09-15T09:15:46.0619347Z",
  "TotalResults": 1
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as arrival and depature dates. 
The filter can also include content filtering, such as only those hotels associated with a particular CBIS category or that have 24 hr reception. 
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
   "PointOfSalesId": {pointOfSalesId},
   "Arrival": "2017-10-14T12:27:58.851Z",
   "Departure": "2017-10-15T12:27:58.851Z",
   "Currency": "SEK",
   "PageSize": 20,
   "Page": 0,
   "PersonConfigurations": [
     {
       "Adults": 1,
       "ChildrenAges": [
         0
       ] 
     }
   ]
 }' 'https://galaxy.test.citybreak.com/api/availability/get'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/availability/get",
{
	method: "POST",
	headers: {
	   "ApiKey:" "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
	   "PointOfSalesId": {pointOfSalesId},
	   "Arrival": "2017-10-14T12:27:58.851Z",
	   "Departure": "2017-10-15T12:27:58.851Z",
	   "Currency": "SEK",
	   "PageSize": 20,
	   "Page": 0,
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
      "Id": 1136433,
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
  "SearchId": "899fe054-3bb4-4ff8-b577-ba716b0b3317",
  "ExpirationDate": "2017-09-15T09:15:46.0619347Z",
  "TotalResults": 1
}
```

*NB under active development* This is a **POST** request that requires a filter with a valid (non-expired) SearchId. The filter otherwise behaves the same as it would in the original <a href="https://visit.github.io/galaxy-docs/#Accommodation">Accommodation</a> search. You can see a bare minimum verison of this search in the examples.

### HTTP Request

`POST https://galaxy.citybreak.com/availability/get`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)
