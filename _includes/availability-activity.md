# Availability - Activity

**Availability - Activity** calls provide information about the availability of activity products. The search will return products with availability, including content, pricing groups, as well as a Search ID with its Expiry. 

The `SearchId` can be used to retrieve prior, cached searches in a much shorter amount of time for Activity Search if used before its Expiry. The object recalled by the search contains all the unfiltered information retrieved in the first search, so further or different filtering on content, etc. can be done in this call.

The `SearchId` and the `BookKey` of each activity quote are used in the basket operations to add the product found to the <a href="#add-activity-booking-item">Basket</a> 


**GET** and **POST** operations 

## Activity

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
   "PointOfSalesId": 0,
   "Date": "2019-02-18",
   "Currency": "NOK",
   "PageSize": 20
 }' 'https://galaxy.citybreak.com/v5/api/availability/activity'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/activity",
{
	method: "POST",
	headers: {
	    "ApiKey": "APIKEY132456789EWOK",
	    "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
	   "PointOfSalesId": 0,
	   "Date": "2019-02-18",
	   "Currency": "NOK",
	   "PageSize": 20
	})  
});
```

> Example of response:

```json
{
  "ActivitySearch": {
    "PointOfSalesId": 0,
    "Date": "2019-02-18T00:00:00",
    "Currency": "NOK",
    "PageSize": 20,
    "Page": 0,
    "Sort": {
      "Order": "Asc",
      "Field": "Price"
    },
    "ContentFilter": null,
    "OutputFilter":{
      "Attributes":[99],
      "Categories": false,
      "Geos": false,
      "Pois": false,
      "Position": false
    }
}
  },
  "ActivityGroups": [
    {
      "Id": "cbis:12345",
      "Name": "Ski Lessons at Lake Tahoe",
      "Content": {
        "PriceFrom": 0,
        "Images": [                            
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=123",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Ski Lessons at Lake Tahoe"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "Activities": [
        {
          "Id": "cbis:1501474",
          "Name": "Ski Lessons for Beginners",
          "MaximumItemsBookable": null,
          "MinimumItemsBookable": 1,
          "Content": {
            "PriceFrom": 0,
            "Images": [],
            "Information": [
              {
                "Id": 99,
                "Name": "Name",
                "Value": "Ski Lessons for Beginners"
              }
            ],
            "Categories": null,
            "Geos": null,
            "Pois": null,
            "Position": null
          },
          "Occasions": [
            {
              "Start": "2019-02-18T09:00:00",
              "Duration": "03:00:00",
              "Quotes": [
                {
                  "BookKey": "123-T",
                  "AvailableCapacity": 4,
                  "Price": {
                    "PriceGroupCode": "ADT",
                    "PriceGroupName": "Adult",
                    "Age": null,
                    "Price": 1000,
                    "OriginalPrice": 1000,
                    "Currency": "NOK"
                  },
                  "BookingConditions": {
                    "Name": null,
                    "Terms": null
                  },
                  "DiscountInformation": {
                    "Name": null,
                    "Description": null
                  },
                  "IncludedAddons": []
                }
                {
                  "BookKey": "124-T",
                  "AvailableCapacity": 3,
                  "Price": {
                    "PriceGroupCode": "CHD",
                    "PriceGroupName": "Youth 7-15",
                    "Age": null,
                    "Price": 500,
                    "OriginalPrice": 500,
                    "Currency": "NOK"
                  },
                  "BookingConditions": {
                    "Name": null,
                    "Terms": null
                  },
                  "DiscountInformation": {
                    "Name": null,
                    "Description": null
                  },
                  "IncludedAddons": []
                },
                {
                  "BookKey": "125-T",
                  "AvailableCapacity": 3,
                  "Price": {
                    "PriceGroupCode": "CHD-DIS",
                    "PriceGroupName": "Youth 7-15",
                    "Age": null,
                    "Price": 410,
                    "OriginalPrice": 0,
                    "Currency": "NOK"
                  },
                  "BookingConditions": {
                    "Name": null,
                    "Terms": null
                  },
                  "DiscountInformation": {
                    "Name": "Sportlovet2019",
                    "Description": "Rabatt för Sportlovet"
                  },
                  "IncludedAddons": [
                    {
                      "Name": "Sportlovet 2019 Hatt",
                      "Content": {
                          "PriceFrom": 0,
                          "Images": [],
                          "Information": [
                              {
                                  "Id": 99,
                                  "Name": "Name",
                                  "Value": "Sportlovet 2019 Hatt"
                              }
                          ],
                          "Categories": null,
                          "Geos": null,
                          "Pois": null,
                          "Position": null
                      },
                      "Price": 10,
                      "Amount": 1,
                      "Currency": "NOK",
                      "PriceIncluded": true
                    }
                  ]
                }
              ]
            },
            {
              "Start": "2019-02-18T14:00:00",
              "Duration": "03:00:00",
              "Quotes": [
                {
                  "BookKey": "126-T",
                  "AvailableCapacity": 7,
                  "Price": {
                    "PriceGroupCode": "ADT",
                    "PriceGroupName": "Adult",
                    "Age": null,
                    "Price": 1000,
                    "OriginalPrice": 1000,
                    "Currency": "NOK"
                  },
                  "BookingConditions": {
                    "Name": null,
                    "Terms": null
                  },
                  "DiscountInformation": {
                    "Name": null,
                    "Description": null
                  },
                  "IncludedAddons": []
                }
              ]
            }
          ]
        },
        {
          "Id": "cbis:1501474",
          "Name": "Advanced Ski Lessons",
          "MaximumItemsBookable": null,
          "MinimumItemsBookable": 1,
          "Content": {
            "PriceFrom": 0,
            "Images": [],
            "Information": [
              {
                "Id": 99,
                "Name": "Name",
                "Value": "Advanced Ski Lessons"
              }
            ],
            "Categories": null,
            "Geos": null,
            "Pois": null,
            "Position": null
          },
          "Occasions": [
            {
              "Start": "2019-02-18T09:00:00",
              "Duration": "04:00:00",
              "Quotes": [
                {
                  "BookKey": "127-T",
                  "AvailableCapacity": 4,
                  "Price": {
                    "PriceGroupCode": "ADT",
                    "PriceGroupName": "Adult",
                    "Age": null,
                    "Price": 1100,
                    "OriginalPrice": 1100,
                    "Currency": "NOK"
                  },
                  "BookingConditions": {
                    "Name": null,
                    "Terms": null
                  },
                  "DiscountInformation": {
                    "Name": null,
                    "Description": null
                  },
                  "IncludedAddons": []
                }
              ]
            }
          ]
        }
      ],
      "TotalResults": 2
    }
  ],
  "SearchId": "2121as12-1a2s-1s2a-2a1s-12as21sa12as",
  "ExpirationDate": "2019-01-29T15:15:46.2172447+01:00",
  "TotalResults": 2,
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

This is a **POST** request that requires a filter with some mandatory properties, such as date.
The filter can also include content filtering, such as only including those activities associated with a particular CBIS category or with certain attributes.
Content filtering possibilities can be found in the <a href="#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The return structure is a list of Activity Groups (such as ski lessons) which contain activities (e.g one for each skill level). Each activity contains Occasions, each of which defines a possible start date, time and duration for the Activity (e.g. morning lessons, afternoon lessons). Finally each occasion has a list of quotes, which are the bookable objects, in each of these you will find all the information related to price groups, prices and other pertinent information and the `BookKey` (e.g. one price for adults, another for children).
The most important return values in the response are the `SearchId` and the `BookKey` found in each `Quote` object, they are used in the <a href="#add-activity-booking-item">Basket</a>, also pay attention to the `ExpirationDate` of the `SearchId`.
It is also worth paying attention to the Minimum and Maximum Items to Book. These are often values set by external systems and if your basket item is outside these parameters it may fail to commit. A `null` value means unrestricted. Booking Conditions and Discount Information relate can contain specific supplier information or Campaign information respectively.
IMPORTANT: Paging is 0-indexed.

### HTTP Request

`POST https://galaxy.citybreak.com/availability/activity`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 0, //int - Mandatory 
  "Date": "2018-12-30", //DateTime - Mandatory
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "PageSize": 0, //int Mandatory, 0-Indexed
  "Sort": { // Optional - defaults to Price Ascending
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string" //string - Mandatory if parent included - Price, Name, Random
  },
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a>
  },
  "OutputFilter": { // Optional -  See <a href="#output-filter">OutputFilter</a>
  }
}
</code>

## Get Previous Search

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
  "Page": 0,
  "PageSize": 20,
  "SearchId": "2121as12-1a2s-1s2a-2a1s-12as21sa12as"
}' 'https://galaxy.citybreak.com/v5/api/availability/activity/get'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/activity/get",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "Page": 0,
    "PageSize": 20,
    "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh"
  })  
});
```

> Example of response:

```json
{
  "ActivitySearch": {
    "PointOfSalesId": 0,
    "Date": "2019-02-18T00:00:00",
    "Currency": "NOK",
    "PageSize": 20,
    "Page": 0,
    "Sort": {
      "Order": "Asc",
      "Field": "Price"
    },
    "ContentFilter": null,
    "OutputFilter": null
  },
  "ActivityGroups": [
    {
      "Id": "cbis:12345",
      "Name": "Off Piste Ski Lessons",
      "Content": {
        "PriceFrom": 0,
        "Images": [                            
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=123",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Off Piste Ski Lessons"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "Activities": [
        {
          "Id": "cbis:1501474",
          "Name": "Advanced Off Piste Ski Lessons",
          "MaximumItemsBookable": null,
          "MinimumItemsBookable": 2,
          "Content": {
            "PriceFrom": 0,
            "Images": [],
            "Information": [
              {
                "Id": 99,
                "Name": "Name",
                "Value": "Advanced Off Piste Ski Lessons"
              }
            ],
            "Categories": null,
            "Geos": null,
            "Pois": null,
            "Position": null
          },
          "Occasions": [
            {
              "Start": "2019-02-18T09:00:00",
              "Duration": "08:00:00",
              "Quotes": [
                {
                  "BookKey": "127-T",
                  "AvailableCapacity": 4,
                  "Price": {
                    "PriceGroupCode": "ADT",
                    "PriceGroupName": "Adult",
                    "Age": null,
                    "Price": 2100,
                    "OriginalPrice": 0,
                    "Currency": "NOK"
                  },
                  "BookingConditions": {
                    "Name": null,
                    "Terms": null
                  },
                  "DiscountInformation": {
                    "Name": null,
                    "Description": null
                  },
                  "IncludedAddons": []
                }
              ]
            }
          ]
        }
      ],
      "TotalResults": 1
    }
  ],
  "SearchId": "2121as12-1a2s-1s2a-2a1s-12as21sa12as",
  "ExpirationDate": "2019-01-29T15:15:46.2172447+01:00",
  "TotalResults": 2
}
```

This is a **POST** request that requires a filter with a valid (non-expired) `SearchId`. The filter otherwise has the same constraints as in the original <a href="#availability---activity">Activity availability</a> search. You can see a bare minimum version of this search in the examples. IMPORTANT: Paging is 0-indexed.

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/activity/get`

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
  //string - Mandatory - the search Id of a still valid activity availability search
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
  "Start": "2018-12-14",
  "End": "2018-12-16",
  "Currency": "DKK"
}' 'https://galaxy.citybreak.com/v5/api/availability/activity/calendar'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/activity/calendar",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 0,
    "Start": "2018-12-13",
    "End": "2018-12-16",
    "Currency": "DKK"
  })  
});
```

> Example of response:

```json
{
  "Days": [
    {
      "Date": "2018-12-14T00:00:00",
      "Activities": [
        "cbis:1234",
        "cbis:1235"
      ]
    },
    {
      "Date": "2018-12-14T00:00:00",
      "Activities": null
    },
    {
      "Date": "2018-12-15T00:00:00",
      "Activities": [
        "cbis:1234",
        "cbis:1235"
        "cbis:1236"
      ]
    },
    {
      "Date": "2018-12-16T00:00:00",
      "Activities": [
        "cbis:1234",
        "cbis:1236"
      ]
    }
  ],
  "CalendarContext": {
    "PointOfSalesId": 0,
    "Start": "2018-12-14T00:00:00",
    "End": "2018-12-16T00:00:00",
    "Currency": "DKK",
    "ContentFilter": {
      "Ids":[
          "cbis:1234",
          "cbis:1235"
          "cbis:1236"
        ]
    }
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
As in other availability queries, the filter can also include a content filter, such as only those activities associated with a particular CBIS category or with certain attributes. 
This is especially handy if you want a very quick look at availability for a specific product or products over a range of days.
Content possibilities can be found in the <a href="#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The return of this call is a set of availble dates (if there is availability) an entity called Activities which is a set of the cbis IDs of the activities (as opposed to activity groups) available on that day. This is useful for, say, quickly displaying days on which you can find available activities. You can use the <a href="#product-content">Product content</a> call with if you also wish to populate a specific activity with content (check the relations field if you want the content of the encapsulating group)
 
### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/activity/calendar/byday`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 0, //int - Mandatory 
  "Start": "2018-12-14", //DateTime - Mandatory, conforms to ISO 8601
  "End": "2018-12-16", //DateTime - Mandatory, conforms to ISO 8601
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a>
  },
}
</code>

## Calendar Search By Product

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
  "PointOfSalesId": 0,
  "Start": "2019-02-16",
  "End": "2019-02-19",
  "Currency": "EUR",
  "ContentFilter": {
    "Ids": [
      "cbis:12345",
      "cbis:12346"
    ]
  },
  "OutputFilter":{
    "Attributes":[99],
    "Categories": false,
    "Geos": false,
    "Pois": false,
    "Position": false
  }
}' 'https://galaxy.citybreak.com/v5/api/availability/activity/calendar/byproduct'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/activity/calendar/byproduct",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 0,
    "Start": "2019-02-16",
    "End": "2019-02-19",
    "Currency": "EUR",
    "ContentFilter": {
      "Ids": [
      "cbis:12345",
      "cbis:12346"
      ]
    },
    "OutputFilter":{
      "Attributes":[99],
      "Categories": false,
      "Geos": false,
      "Pois": false,
      "Position": false
    }
  })  
});
```

> Example of response:

```json
{
  "CalendarContentContext": {
      "PointOfSalesId": 18280,
      "Start": "2019-02-16T00:00:00",
      "End": "2019-02-19T00:00:00",
      "Currency": "EUR",
      "ContentFilter": null,
      "OutputFilter": {
        "Attributes": [
          99
        ],
        "Categories": false,
        "Geos": false,
        "Pois": false,
        "Position": false
      }
  },
  "ActivityGroups": [
    {
      "Id": "cbis:123245",
      "Name": "Rappeling Down the Ice Wall in Pyhä-Luosto",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=1235",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=1235",
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
            "Value": "Rappeling Down the Ice Wall in Pyhä-Luosto"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "Activities": [
        {
          "Id": "cbis:12347",
          "Name": "Rappeling Down the Ice Wall in Pyhä-Luosto",
          "Content": {
            "PriceFrom": null,
            "Images": [],
              "Information": [
                {
                  "Id": 99,
                  "Name": "Name",
                  "Value": "Rappeling Down the Ice Wall in Pyhä-Luosto"
                }
              ],
              "Categories": null,
              "Geos": null,
              "Pois": null,
              "Position": null
          },
          "AvailableDates": [
            "2019-02-16T00:00:00Z",
            "2019-02-18T00:00:00Z",
            "2019-02-19T00:00:00Z"
          ]
        }
      ],
      "TotalResults": 1
    },
    {
      "Id": "cbis:123246",
      "Name": "Climbing up the Ice Wall in Pyhä-Luosto",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=1234",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=1234",
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
            "Value": "Climbing up the Ice Wall in Pyhä-Luosto"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "Activities": [
        {
          "Id": "cbis:12348",
          "Name": "Climbing up the Ice Wall in Pyhä-Luosto",
          "Content": {
            "PriceFrom": null,
            "Images": [],
              "Information": [
                {
                  "Id": 99,
                  "Name": "Name",
                  "Value": "Climbing up the Ice Wall in Pyhä-Luosto"
                }
              ],
              "Categories": null,
              "Geos": null,
              "Pois": null,
              "Position": null
          },
          "AvailableDates": [
            "2019-02-17T00:00:00Z",
            "2019-02-18T00:00:00Z",
            "2019-02-19T00:00:00Z"
          ]
        }
      ],
      "TotalResults": 1
    },
  ],
  "TotalResults": 2,
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
As in other availability queries, the filter can also include a content filter, such as only those activities associated with a particular CBIS category or with certain attributes. 
As there is no paging for the calendar content search it is sensible to request the bare minimum both in terms of products searched and content returned.
Content possibilities can be found in the <a href="#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The return of this call the activity groups and activities that have availabilities within the time range you are looking for, instead of occasions and quotes you simply get a list of days the product is available.
 
### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/activity/calendar/byproduct`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 0, //int - Mandatory 
  "Start": "2018-12-14", //DateTime - Mandatory, conforms to ISO 8601
  "End": "2018-12-16", //DateTime - Mandatory, conforms to ISO 8601
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a>
  },
  "OutputFilter": { // Optional -  See <a href="#output-filter">OutputFilter</a>
  }
}
</code>

