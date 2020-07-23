# Availability - Transport

**Availability - Transport** calls provide information about the availability of any type of transport products. The search will return products with availability, including content, pricing groups, included addons as well as a Search ID with its Expiry. 

The `SearchId` can be used to retrieve prior, cached searches in a much shorter amount of time if used before its Expiry. The object recalled by the search contains all the unfiltered information retrieved in the first search, so further or different filtering on content, etc. can be done in this call.

The `SearchId` and the `BookingKey` of each quote are used in the basket operations to add the product found to the <a href="#add-transport-booking-item">Basket</a> 


**GET** and **POST** operations 

## Transport

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
  "PointOfSalesId":18724,
  "Currency":"NOK",
  "PageSize":50,
  "Page":0,
  "Sort":{
    "Order":"Asc",
    "Field":"Price"
  },
  "Persons":[
    {
      "Code":"997",
      "Quantity":2
    }
  ],
  "Vehicles":[
    {
      "Code":"998",
      "Quantity":1
    }
  ],
  "Routes":[
    {
      "DepartureLocationCode":"25130",
      "DepartureDate":"2020-08-17T00:00:00",
      "ArrivalLocationCode":"25140"
    },
    {
      "DepartureLocationCode":"25140",
      "DepartureDate":"2020-08-18T00:00:00",
      "ArrivalLocationCode":"25130"
    }
  ]
}' 'https://galaxy.citybreak.com/v5/api/availability/transport'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/transport",
{
	method: "POST",
	headers: {
	    "ApiKey": "APIKEY132456789EWOK",
	    "Accept": "application/json",
		"Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId":18724,
    "Currency":"NOK",
    "PageSize":50,
    "Page":0,
    "Sort":{
      "Order":"Asc",
      "Field":"Price"
    },
    "Persons":[
      {
        "Code":"997",
        "Quantity":2
      }
    ],
    "Vehicles":[
      {
        "Code":"998",
        "Quantity":1
      }
    ],
    "Routes":[
      {
        "DepartureLocationCode":"25130",
        "DepartureDate":"2020-08-17T00:00:00",
        "ArrivalLocationCode":"25140"
      },
      {
        "DepartureLocationCode":"25140",
        "DepartureDate":"2020-08-18T00:00:00",
        "ArrivalLocationCode":"25130"
      }
    ]
  })
});
```

> Example of response:

```json
{
  "TransportSearch": {
    "PointOfSalesId": 18724,
    "Currency": "NOK",
    "PageSize": 50,
    "Page": 0,
    "Sort": {
      "Order": "Asc",
      "Field": "Price"
    },
    "Persons": [
      {
        "Code": "997",
        "Quantity": 2
      }
    ],
    "Vehicles": [
      {
        "Code": "998",
        "Quantity": 1
      }
    ],
    "Routes": [
      {
        "DepartureLocationCode": "25130",
        "DepartureDate": "2020-08-17T00:00:00",
        "ArrivalLocationCode": "25140"
      },
      {
        "DepartureLocationCode": "25140",
        "DepartureDate": "2020-08-18T00:00:00",
        "ArrivalLocationCode": "25130"
      }
    ]
  },
  "Locations": [
    {
      "Code": "25130",
      "City": null,
      "Country": null,
      "Name": "Amsterdam",
      "Position": null,
      "State": null,
      "Regions": null
    },
    {
      "Code": "25140",
      "City": null,
      "Country": null,
      "Name": "Newcastle",
      "Position": null,
      "State": null,
      "Regions": null
    }
  ],
  "Fares": [
    {
      "Code": "SVAN",
      "Name": "DFDS",
      "Content": {
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "DFDS"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Choose from a range of cabins to suit your budget. From standard inside or sea view cabins, economy cabins or a premium commodore cabin with breakfast and free WiFi included.\r\nPlease note: Prices per cabin. Infants (0-3 years) can stay in the cabin in addition to the number of beds stated if the infant does not need a separate bed."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "LuggageIncluded": null,
      "MarketingCarrierCode": "DFDS"
    }
  ],
  "Cabins": [
    {
      "Code": "B2",
      "Name": "2-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B2.jpg",
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
            "Value": "2-bed inside cabin with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Internal standard cabin with 2 beds.\r\n• The cabin is designed for 1-2 people\r\n• Bunk beds\r\n• Shower and toilet"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "BD",
      "Name": "2-bed inside cabin with double bed ",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/BD.jpg",
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
            "Value": "2-bed inside cabin with double bed "
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Standard cabin\r\n• The cabin is for 1-2 people\r\n• Small double bed\r\n• Shower and toilet\r\n\r\nStandard Standard Cabin with Small Double Bed."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Carriers": [
    {
      "Code": "DFDS",
      "Name": "DFDS",
      "Content": {
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "DFDS"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Vehicles": [],
  "IncludedAddons": [
    {
      "Code": "NCLCT/ADL_NCLCT/ADL_LandServices",
      "Name": "Land Services Excursion, for all passengers",
      "Content": {
        "Images": [],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Land Services Excursion, for all passengers"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "LandServices Description"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "NCLTC/ADL_NCLTC/ADL_LandServices",
      "Name": "Land Services Excursion, for all passengers",
      "Content": {
        "Images": [],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Land Services Excursion, for all passengers"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "LandServices Description"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Results": [
    {
      "BookKey": "1110008262-T",
      "Price": {
        "Price": 3060,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "15:45:00",
        "CabinCode": "B2",
        "Legs": [
          {
            "DepartureLocationCode": "25130",
            "DepartureTime": "2020-08-17T17:30:00",
            "ArrivalLocationCode": "25140",
            "ArrivalTime": "2020-08-18T09:15:00",
            "Duration": "15:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NLAMS"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLCT/ADL_NCLCT/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "59730793-T",
      "Price": {
        "Price": 3140,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "15:45:00",
        "CabinCode": "BD",
        "Legs": [
          {
            "DepartureLocationCode": "25130",
            "DepartureTime": "2020-08-17T17:30:00",
            "ArrivalLocationCode": "25140",
            "ArrivalTime": "2020-08-18T09:15:00",
            "Duration": "15:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NLAMS"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLCT/ADL_NCLCT/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1600706669-T",
      "Price": {
        "Price": 3470,
        "Currency": "NOK"
      },
      "OutboundJourney": null,
      "HomeboundJourney": {
        "Duration": "16:45:00",
        "CabinCode": "B2",
        "Legs": [
          {
            "DepartureLocationCode": "25140",
            "DepartureTime": "2020-08-18T17:00:00",
            "ArrivalLocationCode": "25130",
            "ArrivalTime": "2020-08-19T09:45:00",
            "Duration": "16:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "GBNEW"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLTC/ADL_NCLTC/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      }
    },
    {
      "BookKey": "293005052-T",
      "Price": {
        "Price": 3550,
        "Currency": "NOK"
      },
      "OutboundJourney": null,
      "HomeboundJourney": {
        "Duration": "16:45:00",
        "CabinCode": "BD",
        "Legs": [
          {
            "DepartureLocationCode": "25140",
            "DepartureTime": "2020-08-18T17:00:00",
            "ArrivalLocationCode": "25130",
            "ArrivalTime": "2020-08-19T09:45:00",
            "Duration": "16:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "GBNEW"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLTC/ADL_NCLTC/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      }
    }
  ],
  "SearchId": "c2b2e3c4-53e0-41ff-8012-8c9da7fa053a",
  "ExpirationDate": "2020-07-22T11:30:18.205109+02:00",
  "TotalResults": 23,
  "Operations": [
    {
      "System": "FerryGateway DFDS",
      "Account": "Ferry Gateway DFDS test EUR",
      "Action": "Search",
      "Duration": "00:00:08.0929013",
      "Success": true,
      "ErrorMessage": null
    }
  ]
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as person configuration and routes. One route has to have both arrival and deprature location codes as well as departure date. In order to preform a return trip search two routes need to be added in search request.
The Most important return values in this response are the `SearchId` and the `BookingKey` used in the <a href="#add-transport-booking-item">Basket</a>, also pay attention to the `ExpirationDate` of the `SearchId`

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/transport`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 0,  //int - Mandatory 
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "PageSize": 0,    //int Mandatory
  "Page": 0,
  "Sort": { // Optional - defaults to Price Ascending
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string"   //string - Mandatory if parent included - Price, Name, Random
  },
  "Persons": [  //Mandatory - Cannot be empty, must represent at least one guest
    {
      "Code": "string", //string - price group code - Mandatory
      "Quantity": 0 //int - number of persons with matching price group code - Mandatory
    }
  ],
  "Vehicles": [ //Optional - vehicle configuration
    {
      "Code": "string", //string - vehicle code - Mandatory if parent included
      "Quantity": 0 //int - number of vehicles with matching vehicle code - Mandatory if parent included
    }
  ],
  "Routes": [   //Mandatory - list of routes
    {
      "DepartureLocationCode": "string",    //string - Mandatory
      "DepartureDate": "2020-07-21T09:45:20.179Z",  //DateTime - Mandatory
      "ArrivalLocationCode": "string"   //string - Mandatory
    }
  ]
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
  "SearchId": "c2b2e3c4-53e0-41ff-8012-8c9da7fa053a"
}' 'https://galaxy.citybreak.com/v5/api/availability/transport/get'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/transport/get",
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
    "SearchId": "c2b2e3c4-53e0-41ff-8012-8c9da7fa053a"
  })  
});
```

> Example of response:

```json
{
  "TransportSearch": {
    "PointOfSalesId": 18724,
    "Currency": "NOK",
    "PageSize": 50,
    "Page": 0,
    "Sort": {
      "Order": "Asc",
      "Field": "Price"
    },
    "Persons": [
      {
        "Code": "997",
        "Quantity": 2
      }
    ],
    "Vehicles": [
      {
        "Code": "998",
        "Quantity": 1
      }
    ],
    "Routes": [
      {
        "DepartureLocationCode": "25130",
        "DepartureDate": "2020-08-17T00:00:00",
        "ArrivalLocationCode": "25140"
      },
      {
        "DepartureLocationCode": "25140",
        "DepartureDate": "2020-08-18T00:00:00",
        "ArrivalLocationCode": "25130"
      }
    ]
  },
  "Locations": [
    {
      "Code": "25130",
      "City": null,
      "Country": null,
      "Name": "Amsterdam",
      "Position": null,
      "State": null,
      "Regions": null
    },
    {
      "Code": "25140",
      "City": null,
      "Country": null,
      "Name": "Newcastle",
      "Position": null,
      "State": null,
      "Regions": null
    }
  ],
  "Fares": [
    {
      "Code": "SVAN",
      "Name": "DFDS",
      "Content": {
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "DFDS"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Choose from a range of cabins to suit your budget. From standard inside or sea view cabins, economy cabins or a premium commodore cabin with breakfast and free WiFi included.\r\nPlease note: Prices per cabin. Infants (0-3 years) can stay in the cabin in addition to the number of beds stated if the infant does not need a separate bed."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "LuggageIncluded": null,
      "MarketingCarrierCode": "DFDS"
    }
  ],
  "Cabins": [
    {
      "Code": "B2",
      "Name": "2-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B2.jpg",
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
            "Value": "2-bed inside cabin with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Internal standard cabin with 2 beds.\r\n• The cabin is designed for 1-2 people\r\n• Bunk beds\r\n• Shower and toilet"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "BD",
      "Name": "2-bed inside cabin with double bed ",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/BD.jpg",
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
            "Value": "2-bed inside cabin with double bed "
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Standard cabin\r\n• The cabin is for 1-2 people\r\n• Small double bed\r\n• Shower and toilet\r\n\r\nStandard Standard Cabin with Small Double Bed."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Carriers": [
    {
      "Code": "DFDS",
      "Name": "DFDS",
      "Content": {
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "DFDS"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Vehicles": [],
  "IncludedAddons": [
    {
      "Code": "NCLCT/ADL_NCLCT/ADL_LandServices",
      "Name": "Land Services Excursion, for all passengers",
      "Content": {
        "Images": [],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Land Services Excursion, for all passengers"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "LandServices Description"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "NCLTC/ADL_NCLTC/ADL_LandServices",
      "Name": "Land Services Excursion, for all passengers",
      "Content": {
        "Images": [],
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "Land Services Excursion, for all passengers"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "LandServices Description"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Results": [
    {
      "BookKey": "1110008262-T",
      "Price": {
        "Price": 3060,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "15:45:00",
        "CabinCode": "B2",
        "Legs": [
          {
            "DepartureLocationCode": "25130",
            "DepartureTime": "2020-08-17T17:30:00",
            "ArrivalLocationCode": "25140",
            "ArrivalTime": "2020-08-18T09:15:00",
            "Duration": "15:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NLAMS"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLCT/ADL_NCLCT/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "59730793-T",
      "Price": {
        "Price": 3140,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "15:45:00",
        "CabinCode": "BD",
        "Legs": [
          {
            "DepartureLocationCode": "25130",
            "DepartureTime": "2020-08-17T17:30:00",
            "ArrivalLocationCode": "25140",
            "ArrivalTime": "2020-08-18T09:15:00",
            "Duration": "15:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NLAMS"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLCT/ADL_NCLCT/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1600706669-T",
      "Price": {
        "Price": 3470,
        "Currency": "NOK"
      },
      "OutboundJourney": null,
      "HomeboundJourney": {
        "Duration": "16:45:00",
        "CabinCode": "B2",
        "Legs": [
          {
            "DepartureLocationCode": "25140",
            "DepartureTime": "2020-08-18T17:00:00",
            "ArrivalLocationCode": "25130",
            "ArrivalTime": "2020-08-19T09:45:00",
            "Duration": "16:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "GBNEW"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLTC/ADL_NCLTC/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      }
    },
    {
      "BookKey": "293005052-T",
      "Price": {
        "Price": 3550,
        "Currency": "NOK"
      },
      "OutboundJourney": null,
      "HomeboundJourney": {
        "Duration": "16:45:00",
        "CabinCode": "BD",
        "Legs": [
          {
            "DepartureLocationCode": "25140",
            "DepartureTime": "2020-08-18T17:00:00",
            "ArrivalLocationCode": "25130",
            "ArrivalTime": "2020-08-19T09:45:00",
            "Duration": "16:45:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "GBNEW"
          }
        ],
        "FareCode": "SVAN",
        "IncludedAddons": [
          {
            "AddonCode": "NCLTC/ADL_NCLTC/ADL_LandServices",
            "Price": 10,
            "Currency": "EUR",
            "PriceIncluded": true
          }
        ]
      }
    }
  ],
  "SearchId": "c2b2e3c4-53e0-41ff-8012-8c9da7fa053a",
  "ExpirationDate": "2020-07-22T11:30:18.205109+02:00",
  "TotalResults": 23,
  "Operations": [
    {
      "System": "FerryGateway DFDS",
      "Account": "Ferry Gateway DFDS test EUR",
      "Action": "Search",
      "Duration": "00:00:08.0929013",
      "Success": true,
      "ErrorMessage": null
    }
  ]
}
```

This is a **POST** request that requires a filter with a valid (non-expired) SearchId. The filter otherwise has the same constraints as in the original <a href="#availability---transport">Transport availability</a> search. You can see a bare minimum version of this search in the examples.

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/transport/get`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "Page":0, //int mandatory - the pager is 0-indexed so 1 is the second page
  "PageSize": 0, //int Mandatory
  "Sort": { // Optional
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string" //string - Mandatory if parent included - Price, Name, Random
  },
  //string - Mandatory - the search Id of a still valid accommodation availability search
  "SearchId":"string"
}
</code>
