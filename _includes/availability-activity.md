# Availability - Activity

**Availability - Activity** calls provide information about the availability of activity products. The search will return products with availability, including content, pricing groups, as well as a Search ID with its Expiry. 

The `SearchId` can be used to retrieve prior, cached searches in a much shorter amount of time for Activity Search if used before its Expiry. The object recalled by the search contains all the unfiltered information retrieved in the first search, so further or different filtering on content, etc. can be done in this call.

The `SearchId` and the `BookingKey` of each room product are used in the basket operations to add the product found to the <a href="https://visit.github.io/galaxy-docs/#basket">Basket</a> 


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
   "Date": "2018-12-30",
   "Currency": "DKK",
   "PageSize": 20
 }' 'https://galaxy.citybreak.com/v3/api/availability/activity'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/activity",
{
	method: "POST",
	headers: {
	    "ApiKey:" "APIKEY132456789EWOK",
	    "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
	   "PointOfSalesId": 0,
	   "Date": "2018-12-30",
	   "Currency": "DKK",
	   "PageSize": 20
	})  
});
```

> Example of response:

```json
{
  "ActivitySearch": {
    "PointOfSalesId": 0,
    "Date": "2018-12-30T00:00:00",
    "Currency": "DKK",
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
      "Id": "cbis:1712391",
      "Name": "Citypass valid 24 H",
      "Content": {
        "PriceFrom": 150,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5856402",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 910,
            "Name": "UrlName",
            "Value": "C24_1712391"
          },
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Citypass valid 24 H"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "<p>Book</p>"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "-"
          }
        ],
        "Categories": null,
        "Geos": [
          {
            "Id": 80708,
            "Path": "Denmark"
          }
        ],
        "Pois": [],
        "Position": null
      },
      "Activities": [
        {
          "Id": "cbis:1712392",
          "Prices": [
            {
              "PriceGroupCode": "PRGR-0",
              "PriceGroupName": "Adult",
              "Age": null,
              "Price": 150,
              "OriginalPrice": 0,
              "Currency": "DKK"
            }
          ],
          "BookingKey": "T-5",
          "Name": "CITYPASS 24H",
          "Start": "2018-12-30T00:00:00",
          "Duration": "00:00:00",
          "Content": {
            "PriceFrom": 150,
            "Images": [
              {
                "Uri": "//images.citybreak.com/image.aspx?ImageId=5856403",
                "IsMain": true,
                "Name": null,
                "Copyright": null,
                "Description": null
              }
            ],
            "Information": [
              {
                "Id": 910,
                "Name": "UrlName",
                "Value": "CITYP24_1712392"
              },
              {
                "Id": 99,
                "Name": "Name",
                "Value": "CITYPASS 24H"
              },
              {
                "Id": 101,
                "Name": "Introduction",
                "Value": "CITYPASS 24H"
              },
              {
                "Id": 102,
                "Name": "Description",
                "Value": "-"
              }
            ],
            "Categories": null,
            "Geos": [
              {
                "Id": 80708,
                "Path": "Denmark"
              }
            ],
            "Pois": [],
            "Position": null
          },
          "IncludedAddons": [],
          "AvailableCapacity": 9999,
          "BookingConditions": null,
          "DiscountInformation": null
        }
      ],
      "TotalResults": 1
    }
  ],
  "SearchId": "2608ec73-7b58-4dc0-8f67-4d0428d5051f",
  "ExpirationDate": "2018-12-21T15:15:46.2172447+01:00",
  "TotalResults": 1
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as date. 
The filter can also include content filtering, such as only including those activities associated with a particular CBIS category or with certain attributes.
Content filtering possibilities can be found in the <a href="https://visit.github.io/galaxy-docs/#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The Most important return values in this response are the `SearchId` and the `BookingKey` used in the <a href="https://visit.github.io/galaxy-docs/#basket">Basket</a>, also pay attention to the `ExpirationDate` of the `SearchId`

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
  "PageSize": 0, //int Mandatory
  "Sort": { // Optional - defaults to Price Ascending
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string" //string - Mandatory if parent included - Price, Name, Random
  },
  "ContentFilter": { // Optional - See <a href="https://visit.github.io/galaxy-docs/#content-filter">ContentFilter</a>
  },
  "OutputFilter": { // Optional -  See <a href="https://visit.github.io/galaxy-docs/#output-filter">OutputFilter</a>
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
  "Page": 1,
  "PageSize": 20,
  "SearchId": "aaaa1234-4321-1a2b-asdf-123456asdfgh"
}' 'https://galaxy.citybreak.com/v3/api/availability/activity/get'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/activity/get",
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
  "ActivitySearch": {
    "PointOfSalesId": 0,
    "Date": "2018-12-30T00:00:00",
    "Currency": "DKK",
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
      "Id": "cbis:1712391",
      "Name": "Citypass valid 24 H",
      "Content": {
        "PriceFrom": 150,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=5856402",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 910,
            "Name": "UrlName",
            "Value": "C24_1712391"
          },
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Citypass valid 24 H"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "<p>Book</p>"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "-"
          }
        ],
        "Categories": null,
        "Geos": [
          {
            "Id": 80708,
            "Path": "Denmark"
          }
        ],
        "Pois": [],
        "Position": null
      },
      "Activities": [
        {
          "Id": "cbis:1712392",
          "Prices": [
            {
              "PriceGroupCode": "PRGR-0",
              "PriceGroupName": "Adult",
              "Age": null,
              "Price": 150,
              "OriginalPrice": 0,
              "Currency": "DKK"
            }
          ],
          "BookingKey": "T-5",
          "Name": "CITYPASS 24H",
          "Start": "2018-12-30T00:00:00",
          "Duration": "00:00:00",
          "Content": {
            "PriceFrom": 150,
            "Images": [
              {
                "Uri": "//images.citybreak.com/image.aspx?ImageId=5856403",
                "IsMain": true,
                "Name": null,
                "Copyright": null,
                "Description": null
              }
            ],
            "Information": [
              {
                "Id": 910,
                "Name": "UrlName",
                "Value": "CITYP24_1712392"
              },
              {
                "Id": 99,
                "Name": "Name",
                "Value": "CITYPASS 24H"
              },
              {
                "Id": 101,
                "Name": "Introduction",
                "Value": "CITYPASS 24H"
              },
              {
                "Id": 102,
                "Name": "Description",
                "Value": "-"
              }
            ],
            "Categories": null,
            "Geos": [
              {
                "Id": 80708,
                "Path": "Denmark"
              }
            ],
            "Pois": [],
            "Position": null
          },
          "IncludedAddons": [],
          "AvailableCapacity": 9999,
          "BookingConditions": null,
          "DiscountInformation": null
        }
      ],
      "TotalResults": 1
    }
  ],
  "SearchId": "2608ec73-7b58-4dc0-8f67-4d0428d5051f",
  "ExpirationDate": "2018-12-21T15:15:46.2172447+01:00",
  "TotalResults": 1
}
```

This is a **POST** request that requires a filter with a valid (non-expired) SearchId. The filter otherwise has the same constraints as in the original <a href="https://visit.github.io/galaxy-docs/#activity">Activity availability</a> search. You can see a bare minimum version of this search in the examples.

### HTTP Request

`POST https://galaxy.citybreak.com/v3/api/availability/activity/get`

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
  "OutputFilter": { // Optional -  See <a href="https://visit.github.io/galaxy-docs/#output-filter">OutputFilter</a>
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
}' 'https://galaxy.citybreak.com/v3/api/availability/activity/calendar'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/availability/activity/calendar",
{
	method: "POST",
	headers: {
	   "ApiKey:" "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 0,
    "Start": "2018-12-14",
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
      "IsAvailable": true,
      "Activities": [
        {
          "Id": "pt:519594",
          "Availability": 9999,
          "Price": 150,
          "StartDate": "2018-12-14T00:00:00",
          "EndDate": null
        },
        {
          "Id": "pt:519759",
          "Availability": 9999,
          "Price": 300,
          "StartDate": "2018-12-14T00:00:00",
          "EndDate": null
        }
      ]
    },
    {
      "Date": "2018-12-15T00:00:00",
      "IsAvailable": true,
      "Activities": [
        {
          "Id": "pt:519594",
          "Availability": 9999,
          "Price": 150,
          "StartDate": "2018-12-15T00:00:00",
          "EndDate": null
        },
        {
          "Id": "pt:519759",
          "Availability": 9999,
          "Price": 300,
          "StartDate": "2018-12-15T00:00:00",
          "EndDate": null
        }
      ]
    },
    {
      "Date": "2018-12-16T00:00:00",
      "IsAvailable": true,
      "Activities": [
        {
          "Id": "pt:519594",
          "Availability": 9999,
          "Price": 150,
          "StartDate": "2018-12-16T00:00:00",
          "EndDate": null
        },
        {
          "Id": "pt:519759",
          "Availability": 9999,
          "Price": 300,
          "StartDate": "2018-12-16T00:00:00",
          "EndDate": null
        }
      ]
    }
  ],
  "CalendarContext": {
    "PointOfSalesId": 0,
    "Start": "2018-12-14T00:00:00",
    "End": "2018-12-16T00:00:00",
    "Currency": "DKK",
    "ContentFilter": null
  }
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as the start and end dates of the calendar, the pointOfSalesId and the currency. 
As in other availability queries, the filter can also include a content filter, such as only those activities associated with a particular CBIS category or with certain attributes. 
Content possibilities can be found in the <a href="https://visit.github.io/galaxy-docs/#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The return of this call is a set of days with an IsAvailable boolean value indicating any availability at all and (if there is availability) an entity called Activities which shows activity options available on that day. This is useful for, say, quickly displaying days on which you can find available activities.
 
### HTTP Request

`POST https://galaxy.citybreak.com/v3/api/availability/activity/calendar`

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
  "ContentFilter": { // Optional - See <a href="https://visit.github.io/galaxy-docs/#content-filter">ContentFilter</a>
  },
}
</code>