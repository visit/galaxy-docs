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
  "PointOfSalesId": 13723,
  "Currency": "NOK",
  "PageSize": 50,
  "ContentFilter": {
	  "Ids": [
		"cbis:822973"
	  ]
  },
  "Persons": [
    {
      "Code": "474",
      "Quantity": 1
    }
  ],
  "Routes": [
    {
      "DepartureLocationCode": "18431",
      "DepartureDate": "2020-09-17",
      "ArrivalLocationCode": "18430"
    },
    {
      "DepartureLocationCode": "18430",
      "DepartureDate": "2020-09-17",
      "ArrivalLocationCode": "18431"
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
  "PointOfSalesId": 13723,
  "Currency": "NOK",
  "PageSize": 50,
  "ContentFilter": {
	  "Ids": [
		"cbis:822973"
	  ]
  },
  "Persons": [
    {
      "Code": "474",
      "Quantity": 1
    }
  ],
  "Routes": [
    {
      "DepartureLocationCode": "18431",
      "DepartureDate": "2020-09-17",
      "ArrivalLocationCode": "18430"
    },
    {
      "DepartureLocationCode": "18430",
      "DepartureDate": "2020-09-17",
      "ArrivalLocationCode": "18431"
    }
  ]
  })
});
```

> Example of response:

```json
{
  "TransportSearch": {
    "PointOfSalesId": 13723,
    "Currency": "NOK",
    "PageSize": 50,
    "Page": 0,
    "Sort": {
      "Order": "Asc",
      "Field": "Price"
    },
    "ContentFilter": {
      "Geos": [],
      "Categories": [],
      "Pois": [],
      "Search": null,
      "Position": null,
      "Information": null,
      "Ids": [
        "cbis:822973"
      ]
    },
    "Persons": [
      {
        "Code": "474",
        "Quantity": 1
      }
    ],
    "Vehicles": [],
    "Routes": [
      {
        "DepartureLocationCode": "18431",
        "DepartureDate": "2020-09-17T00:00:00",
        "ArrivalLocationCode": "18430"
      },
      {
        "DepartureLocationCode": "18430",
        "DepartureDate": "2020-09-17T00:00:00",
        "ArrivalLocationCode": "18431"
      }
    ],
    "PromoCode": null
  },
  "Locations": [
    {
      "Code": "0",
      "City": "Hellesylt",
      "Country": null,
      "Name": "Hellesylt",
      "Position": null,
      "State": null,
      "Regions": null
    }
  ],
  "Fares": [
    {
      "Code": "20GCF",
      "Name": "20GCF",
      "Content": {
        "Id": null,
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "20GCF"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "LuggageIncluded": null,
      "MarketingCarrierCode": "TF"
    },
    {
      "Code": "20GCFR",
      "Name": "20GCFR",
      "Content": {
        "Id": null,
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "20GCFR"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      },
      "LuggageIncluded": null,
      "MarketingCarrierCode": "TF"
    }
  ],
  "Cabins": [
    {
      "Code": "",
      "Name": null,
      "Content": {
        "Id": null,
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": null
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Content": [
    {
      "Id": "cbis:822973",
      "Images": [
        {
          "Uri": "//images.test.citybreak.com/image.aspx?ImageId=4020176",
          "IsMain": false,
          "Name": null,
          "Copyright": null,
          "Description": null
        },
        {
          "Uri": "//images.test.citybreak.com/image.aspx?ImageId=4020185",
          "IsMain": true,
          "Name": null,
          "Copyright": null,
          "Description": null
        },
        {
          "Uri": "//images.test.citybreak.com/image.aspx?ImageId=4577969",
          "IsMain": false,
          "Name": null,
          "Copyright": null,
          "Description": null
        }
      ],
      "Information": [
        {
          "Id": 141,
          "Name": "Price from",
          "Value": "310"
        },
        {
          "Id": 297,
          "Name": "Zoom level",
          "Value": "14"
        },
        {
          "Id": 910,
          "Name": "UrlName",
          "Value": "Fjord_Cruise_Geirangerfjorden_bat_822973"
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
          "Value": "Fjord Cruise Geirangerfjord"
        },
        {
          "Id": 101,
          "Name": "Introduction",
          "Value": "One of the most famous fjords in the world."
        },
        {
          "Id": 102,
          "Name": "Description",
          "Value": "Geirangerfjord is known as the real jewel of the Norwegian fjords. With its characteristic S shape, high waterfalls and abandoned mountain farms, the fjord landscape is included on UNESCO's list of World Heritage sites. Here you find unspoilt and beautiful nature and cultural experiences the whole year round!\r\n\r\nNB! When booking a vehicle, the driver is included in the price!\r\nNB! Select \"1 traveller\" when ordering the Carpackage! This product includes: car, driver and up to 4 passengers."
        },
        {
          "Id": 402,
          "Name": "Currency",
          "Value": "NOK"
        },
        {
          "Id": 415,
          "Name": "Price description",
          "Value": "Per person"
        },
        {
          "Id": 710,
          "Name": "Departure from",
          "Value": "Geiranger & Hellesylt"
        },
        {
          "Id": 100017,
          "Name": "Summer",
          "Value": "True"
        },
        {
          "Id": 100587,
          "Name": "All year",
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
          "Value": "True"
        },
        {
          "Id": 100739,
          "Name": "Spring",
          "Value": "True"
        },
        {
          "Id": 100847,
          "Name": "January",
          "Value": "False"
        },
        {
          "Id": 100848,
          "Name": "February",
          "Value": "False"
        },
        {
          "Id": 100849,
          "Name": "March",
          "Value": "False"
        },
        {
          "Id": 100850,
          "Name": "April",
          "Value": "False"
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
          "Value": "False"
        },
        {
          "Id": 100858,
          "Name": "December",
          "Value": "False"
        },
        {
          "Id": 100939,
          "Name": "Monday",
          "Value": "True"
        },
        {
          "Id": 100940,
          "Name": "Tuesday",
          "Value": "True"
        },
        {
          "Id": 100941,
          "Name": "Wednesday",
          "Value": "True"
        },
        {
          "Id": 100942,
          "Name": "Thursday",
          "Value": "True"
        },
        {
          "Id": 100943,
          "Name": "Friday",
          "Value": "True"
        },
        {
          "Id": 100944,
          "Name": "Saturday",
          "Value": "True"
        },
        {
          "Id": 100945,
          "Name": "Sunday",
          "Value": "True"
        },
        {
          "Id": 102390,
          "Name": "All days",
          "Value": "False"
        },
        {
          "Id": 102391,
          "Name": "No (bicycles not allowed)",
          "Value": "False"
        },
        {
          "Id": 102392,
          "Name": "Yes (bicycles allowed)",
          "Value": "False"
        },
        {
          "Id": 102393,
          "Name": "Everyone",
          "Value": "False"
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
          "Id": 102679,
          "Name": "One departure per day",
          "Value": "False"
        },
        {
          "Id": 102682,
          "Name": "Several departures per day",
          "Value": "True"
        },
        {
          "Id": 102683,
          "Name": "1-2 hours",
          "Value": "True"
        },
        {
          "Id": 102684,
          "Name": "2-4 hours",
          "Value": "False"
        },
        {
          "Id": 102685,
          "Name": "4-6 hours",
          "Value": "False"
        },
        {
          "Id": 102686,
          "Name": "One day",
          "Value": "False"
        },
        {
          "Id": 102687,
          "Name": "Several days",
          "Value": "False"
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
        },
        {
          "Id": 26397,
          "Path": "Aurland (Visit Flåm)"
        },
        {
          "Id": 26401,
          "Path": "To do"
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
          "Id": 86110,
          "Path": "Geirangerfjorden"
        }
      ],
      "Pois": [],
      "Position": {
        "Latitude": 62.1020583040084,
        "Longitude": 7.20629342263521
      }
    }
  ],
  "Carriers": [
    {
      "Code": "TF",
      "Name": "The Fjords",
      "Content": {
        "Id": null,
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "The Fjords"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "Vehicles": [
    {
      "Code": "GE1",
      "Name": "GE1",
      "Content": {
        "Id": null,
        "Images": null,
        "Information": [
          {
            "Id": 99,
            "Name": "Name",
            "Value": "GE1"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    }
  ],
  "IncludedAddons": [],
  "Results": [
    {
      "BookKey": "896582862-T",
      "Price": {
        "Price": 470,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T09:30:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T10:35:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5203"
          }
        ],
        "FareCode": "20GCF",
        "IncludedAddons": [],
        "AvailableCapacity": 50
      },
      "PromoCodeDescription": null,
      "HomeboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T11:00:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T12:05:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5204"
          }
        ],
        "FareCode": "20GCFR",
        "IncludedAddons": [],
        "AvailableCapacity": 40
      }
    },
    {
      "BookKey": "43279953-T",
      "Price": {
        "Price": 470,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T09:30:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T10:35:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5203"
          }
        ],
        "FareCode": "20GCF",
        "IncludedAddons": [],
        "AvailableCapacity": 60
      },
      "PromoCodeDescription": null,
      "HomeboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T14:00:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T15:05:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5208"
          }
        ],
        "FareCode": "20GCFR",
        "IncludedAddons": [],
        "AvailableCapacity": 0
      }
    },
    {
      "BookKey": "1748076464-T",
      "Price": {
        "Price": 470,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T09:30:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T10:35:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5203"
          }
        ],
        "FareCode": "20GCF",
        "IncludedAddons": [],
        "AvailableCapacity": 30
      },
      "PromoCodeDescription": null,
      "HomeboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T17:00:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T18:05:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5212"
          }
        ],
        "FareCode": "20GCFR",
        "IncludedAddons": [],
        "AvailableCapacity": 50
      }
    },
    {
      "BookKey": "909609591-T",
      "Price": {
        "Price": 470,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T12:30:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T13:35:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5207"
          }
        ],
        "FareCode": "20GCF",
        "IncludedAddons": [],
        "AvailableCapacity": 25
      },
      "PromoCodeDescription": null,
      "HomeboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T14:00:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T15:05:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5208"
          }
        ],
        "FareCode": "20GCFR",
        "IncludedAddons": [],
        "AvailableCapacity": 35
      }
    },
    {
      "BookKey": "1717088448-T",
      "Price": {
        "Price": 470,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T12:30:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T13:35:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5207"
          }
        ],
        "FareCode": "20GCF",
        "IncludedAddons": [],
        "AvailableCapacity": 55
      },
      "PromoCodeDescription": null,
      "HomeboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T17:00:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T18:05:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5212"
          }
        ],
        "FareCode": "20GCFR",
        "IncludedAddons": [],
        "AvailableCapacity": 75
      }
    },
    {
      "BookKey": "1121434601-T",
      "Price": {
        "Price": 470,
        "Currency": "NOK"
      },
      "OutboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T15:30:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T16:35:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5211"
          }
        ],
        "FareCode": "20GCF",
        "IncludedAddons": [],
        "AvailableCapacity": 85
      },
      "PromoCodeDescription": null,
      "HomeboundJourney": {
        "Duration": "01:05:00",
        "CabinCode": "",
        "ContentCode": "cbis:822973",
        "Legs": [
          {
            "DepartureLocationCode": "0",
            "DepartureTime": "2020-09-17T17:00:00",
            "ArrivalLocationCode": "0",
            "ArrivalTime": "2020-09-17T18:05:00",
            "Duration": "01:05:00",
            "OperatingCarrierCode": "TF",
            "VehicleCode": "GE1",
            "TransportNumber": "5212"
          }
        ],
        "FareCode": "20GCFR",
        "IncludedAddons": [],
        "AvailableCapacity": 95
      }
    }
  ],
  "PromoCodeStatus": "None",
  "SearchId": "119b7042-0fb6-4918-9775-5b8854734c51",
  "ExpirationDate": "2020-09-11T13:07:36.0248923+02:00",
  "TotalResults": 6,
  "Operations": [
    {
      "System": "Inventory (The Fjords)",
      "Account": "Inventory Pakke (The Fjords)",
      "Action": "Search",
      "Duration": "00:00:23.3486751",
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
  "Sort": { // Optional - defaults to Price Ascending
    "Order": "Asc", //string - Mandatory if parent included
    "Field": "string"   //string - Mandatory if parent included - Price, Name, Random
  },
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a>
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
  ],
  "PromoCode": "string" // string - Optional
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
    "ContentFilter": null,
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
  "Content": [],
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
        ],
        "AvailableCapacity": 50
      },
      "PromoCodeDescription": null,
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
        ],
        "AvailableCapacity": 60
      },
      "PromoCodeDescription": null,
      "HomeboundJourney": null
    },
    {
      "BookKey": "1600706669-T",
      "Price": {
        "Price": 3470,
        "Currency": "NOK"
      },
      "OutboundJourney": null,
      "PromoCodeDescription": null,
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
        ],
        "AvailableCapacity": 75
      }
    },
    {
      "BookKey": "293005052-T",
      "Price": {
        "Price": 3550,
        "Currency": "NOK"
      },
      "OutboundJourney": null,
      "PromoCodeDescription": null,
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
        ],
        "AvailableCapacity": 85
      }
    }
  ],
  "PromoCodeStatus": "None",
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

## Calendar Search By Day

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
  "PointOfSalesId": 13723,
  "Start": "2020-10-01",
  "End": "2020-10-07",
  "Currency": "NOK"
}' 'https://galaxy.citybreak.com/v5/api/availability/transport/calendar/byday'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/transport/calendar/byday",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 13723,
    "Start": "2020-10-01",
    "End": "2020-10-07",
    "Currency": "NOK"
  })  
});
```

> Example of response:

```json
{
  "Days": [
    {
      "Date": "2020-10-01T00:00:00",
      "Transports": [
        "cbis:1614826",
        "cbis:903744"
      ],
      "TransportDetails": [
        {
          "Id": "cbis:1614826",
          "Availability": 384,
          "PriceFrom": null,
          "StartDate": "2020-10-01T00:00:00+02:00"
        },
        {
          "Id": "cbis:903744",
          "Availability": 120,
          "PriceFrom": null,
          "StartDate": "2020-10-01T00:00:00+02:00"
        }
      ]
    },
    {
      "Date": "2020-10-02T00:00:00",
      "Transports": [
        "cbis:1614826",
        "cbis:903744"
      ],
      "TransportDetails": [
        {
          "Id": "cbis:1614826",
          "Availability": 384,
          "PriceFrom": null,
          "StartDate": "2020-10-02T00:00:00+02:00"
        },
        {
          "Id": "cbis:903744",
          "Availability": 120,
          "PriceFrom": null,
          "StartDate": "2020-10-02T00:00:00+02:00"
        }
      ]
    },
    {
      "Date": "2020-10-03T00:00:00",
      "Transports": [
        "cbis:1614826",
        "cbis:903744"
      ],
      "TransportDetails": [
        {
          "Id": "cbis:1614826",
          "Availability": 384,
          "PriceFrom": null,
          "StartDate": "2020-10-03T00:00:00+02:00"
        },
        {
          "Id": "cbis:903744",
          "Availability": 120,
          "PriceFrom": null,
          "StartDate": "2020-10-03T00:00:00+02:00"
        }
      ]
    },
    {
      "Date": "2020-10-04T00:00:00",
      "Transports": [
        "cbis:1614826",
        "cbis:903744"
      ],
      "TransportDetails": [
        {
          "Id": "cbis:1614826",
          "Availability": 384,
          "PriceFrom": null,
          "StartDate": "2020-10-04T00:00:00+02:00"
        },
        {
          "Id": "cbis:903744",
          "Availability": 120,
          "PriceFrom": null,
          "StartDate": "2020-10-04T00:00:00+02:00"
        }
      ]
    },
    {
      "Date": "2020-10-05T00:00:00",
      "Transports": [
        "cbis:1614826",
        "cbis:903744"
      ],
      "TransportDetails": [
        {
          "Id": "cbis:1614826",
          "Availability": 384,
          "PriceFrom": null,
          "StartDate": "2020-10-05T00:00:00+02:00"
        },
        {
          "Id": "cbis:903744",
          "Availability": 120,
          "PriceFrom": null,
          "StartDate": "2020-10-05T00:00:00+02:00"
        }
      ]
    },
    {
      "Date": "2020-10-06T00:00:00",
      "Transports": [
        "cbis:1614826",
        "cbis:903744"
      ],
      "TransportDetails": [
        {
          "Id": "cbis:1614826",
          "Availability": 384,
          "PriceFrom": null,
          "StartDate": "2020-10-06T00:00:00+02:00"
        },
        {
          "Id": "cbis:903744",
          "Availability": 120,
          "PriceFrom": null,
          "StartDate": "2020-10-06T00:00:00+02:00"
        }
      ]
    },
    {
      "Date": "2020-10-07T00:00:00",
      "Transports": [
        "cbis:1614826",
        "cbis:903744"
      ],
      "TransportDetails": [
        {
          "Id": "cbis:1614826",
          "Availability": 384,
          "PriceFrom": null,
          "StartDate": "2020-10-07T00:00:00+02:00"
        },
        {
          "Id": "cbis:903744",
          "Availability": 120,
          "PriceFrom": null,
          "StartDate": "2020-10-07T00:00:00+02:00"
        }
      ]
    },
  ],
  "PromoCodeStatus": "None",
  "CalendarContext": {
    "PointOfSalesId": 13723,
    "Start": "2020-10-01T00:00:00",
    "End": "2020-10-07T00:00:00",
    "Currency": "NOK",
    "ContentFilter": null,
    "PromoCode": null
  },
  "Operations": [
    {
      "System": "Inventory (The Fjords)",
      "Account": "Inventory Pakke (The Fjords)",
      "Action": "Search",
      "Duration": "00:00:00.4750171",
      "Success": true,
      "ErrorMessage": null
    },
    {
      "System": "Inventory (Flåmsbana)",
      "Account": "Inventory (Flåmsbana)",
      "Action": "Search",
      "Duration": "00:00:00.0649991",
      "Success": true,
      "ErrorMessage": null
    },
    {
      "System": "Inventory (Sognefjorden)",
      "Account": "Inventory Pakke (Sognefjorden)",
      "Action": "Search",
      "Duration": "00:00:00.1220060",
      "Success": true,
      "ErrorMessage": null
    }
  ]
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as the start and end dates of the calendar, the pointOfSalesId and the currency. 
As in other availability queries, the filter can also include a content filter, such as only those transport products associated with a particular CBIS category or with certain attributes. 
This is especially handy if you want a very quick look at availability for a specific product or products over a range of days.
Content possibilities can be found in the <a href="#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The return of this call is a set of available dates (if there is availability) an entity called Transports which is a set of the cbis IDs of the transport products available on that day. This is useful for, say, quickly displaying days on which you can find available transports. You can use the <a href="#product-content">Product content</a> call if you also wish to populate a specific transport with content.
 
### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/transport/calendar/byday`

### Query Parameters

Parameter | Description
--------- | -----------
filter | the POST filter
Accept-Language | The language culture (e.g en-us)

<code class="center-column">
{
  "PointOfSalesId": 13723, //int - Mandatory 
  "Start": "2020-10-01", //DateTime - Mandatory, conforms to ISO 8601
  "End": "2020-10-07", //DateTime - Mandatory, conforms to ISO 8601
  "Currency": "string", //string - Mandatory e.g SEK or EUR
  "ContentFilter": { // Optional - See <a href="#content-filter">ContentFilter</a>
  },
  "PromoCode": "string" // string - Optional
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
  "PointOfSalesId": 13723,
  "Start": "2020-10-01",
  "End": "2020-10-07",
  "Currency": "NOK",
  "ContentFilter": {
    "Ids": [
      "cbis:1614826",
      "cbis:903744"
    ]
  }
}' 'https://galaxy.citybreak.com/v5/api/availability/transport/calendar/byproduct'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/availability/transport/calendar/byproduct",
{
	method: "POST",
	headers: {
	   "ApiKey": "APIKEY132456789EWOK",
	   "Accept": "application/json",
		 "Accept-Language": "en-US"
	},
	body: JSON.Stringify({
    "PointOfSalesId": 13723,
    "Start": "2020-10-01",
    "End": "2020-10-07",
    "Currency": "NOK",
    "ContentFilter": {
      "Ids": [
        "cbis:1614826",
        "cbis:903744"
      ]
    }
  })  
});
```

> Example of response:

```json
{
  "CalendarContentContext": {
    "PointOfSalesId": 13723,
    "Start": "2020-10-01T00:00:00",
    "End": "2020-10-07T00:00:00",
    "Currency": "NOK",
    "ContentFilter": null,
    "PromoCode": null
  },
  "TransportActivityCalendars": [
    {
      "Id": "cbis:1614826",
      "Name": "Nærøyfjord Sightseeing B2B ",
      "References": [
        "cbis:1614826",
        "pt:497702"
      ],
      "Content": {
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
            "Value": "Experience the Aurland fjord and Nærøy fjord up close. We travel from Flåm to Gudvangen and make sure you get back to the starting-point when you desire. "
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Experience the Aurlandsfjord and Nærøyfjord, which is on the UNESCO world heritage list up close. \r\nThe route between Flåm and Gudvangen is one of the most popular fjord areas in all of Norway! The spectacular Nærøyfjord is surrounding by steep mountains (up to 1400m high) and beautiful waterfalls. \r\n\r\nEnjoy the silence and nature up close from one of our sightseeing boats. \r\n\r\nChoose between many departures and assemble your journey as you please.  For our disabeld guests we recommend our Premium vessels with universal design.\r\n\r\nOn board our boats we serve refreshments and light meals. "
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
      },
      "AvailableDates": [
        "2020-10-01T00:00:00+02:00",
        "2020-10-02T00:00:00+02:00",
        "2020-10-03T00:00:00+02:00",
        "2020-10-04T00:00:00+02:00",
        "2020-10-05T00:00:00+02:00",
        "2020-10-06T00:00:00+02:00",
        "2020-10-07T00:00:00+02:00"
      ]
    },
    {
      "Id": "cbis:903744",
      "Name": "The Flåm Railway + hiking the Flåm valley",
      "References": [
        "cbis:903744",
        "pt:476556"
      ],
      "Content": {
        "Id": "cbis:903744",
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=3151120",
            "IsMain": true,
            "Name": null,
            "Copyright": null,
            "Description": null
          },
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=4855502",
            "IsMain": false,
            "Name": null,
            "Copyright": null,
            "Description": null
          }
        ],
        "Information": [
          {
            "Id": 141,
            "Name": "Price from",
            "Value": "370"
          },
          {
            "Id": 297,
            "Name": "Zoom level",
            "Value": "18"
          },
          {
            "Id": 910,
            "Name": "UrlName",
            "Value": "Ga_Flamsdalen_903744"
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
            "Value": "The Flåm Railway + hiking the Flåm valley"
          },
          {
            "Id": 101,
            "Name": "Introduction",
            "Value": "Explore the Flåm Valley on foot. "
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Take the world famous Flåm Railway and from Myrdal station start descending the 20 km path through the fjord valley full of history and outstanding nature. \r\n\r\nIf your are planning on bringing your own bike, make sure you also reserve space for your bicycle!"
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
            "Id": 1016,
            "Name": "Concierge high light",
            "Value": "False"
          },
          {
            "Id": 100017,
            "Name": "Summer",
            "Value": "True"
          },
          {
            "Id": 100587,
            "Name": "All year",
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
            "Value": "True"
          },
          {
            "Id": 100739,
            "Name": "Spring",
            "Value": "False"
          },
          {
            "Id": 100847,
            "Name": "January",
            "Value": "False"
          },
          {
            "Id": 100848,
            "Name": "February",
            "Value": "False"
          },
          {
            "Id": 100849,
            "Name": "March",
            "Value": "False"
          },
          {
            "Id": 100850,
            "Name": "April",
            "Value": "False"
          },
          {
            "Id": 100851,
            "Name": "May",
            "Value": "False"
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
            "Value": "False"
          },
          {
            "Id": 100858,
            "Name": "December",
            "Value": "False"
          },
          {
            "Id": 100939,
            "Name": "Monday",
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
            "Value": "False"
          },
          {
            "Id": 102391,
            "Name": "No (bicycles not allowed)",
            "Value": "False"
          },
          {
            "Id": 102392,
            "Name": "Yes (bicycles allowed)",
            "Value": "False"
          },
          {
            "Id": 102393,
            "Name": "Everyone",
            "Value": "False"
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
            "Id": 102679,
            "Name": "One departure per day",
            "Value": "False"
          },
          {
            "Id": 102682,
            "Name": "Several departures per day",
            "Value": "True"
          },
          {
            "Id": 102683,
            "Name": "1-2 hours",
            "Value": "False"
          },
          {
            "Id": 102684,
            "Name": "2-4 hours",
            "Value": "True"
          },
          {
            "Id": 102685,
            "Name": "4-6 hours",
            "Value": "False"
          },
          {
            "Id": 102686,
            "Name": "One day",
            "Value": "False"
          },
          {
            "Id": 102687,
            "Name": "Several days",
            "Value": "False"
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
            "Id": 26404,
            "Path": "The Flam Railway"
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
          },
          {
            "Id": 26397,
            "Path": "Aurland (Visit Flåm)"
          },
          {
            "Id": 26401,
            "Path": "To do"
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
          "Latitude": 60.8630749407715,
          "Longitude": 7.11482355210421
        }
      },
      "AvailableDates": [
        "2020-10-01T00:00:00+02:00",
        "2020-10-02T00:00:00+02:00",
        "2020-10-03T00:00:00+02:00",
        "2020-10-04T00:00:00+02:00",
        "2020-10-05T00:00:00+02:00",
        "2020-10-06T00:00:00+02:00",
        "2020-10-07T00:00:00+02:00"
      ]
    }
  ],
  "PromoCodeStatus": "None",
  "TotalResults": 2,
  "Operations": [
    {
      "System": "Inventory (The Fjords)",
      "Account": "Inventory Pakke (The Fjords)",
      "Action": "Search",
      "Duration": "00:00:01.1570994",
      "Success": true,
      "ErrorMessage": null
    },
    {
      "System": "Inventory (Flåmsbana)",
      "Account": "Inventory (Flåmsbana)",
      "Action": "Search",
      "Duration": "00:00:00.1569712",
      "Success": true,
      "ErrorMessage": null
    },
    {
      "System": "Inventory (Sognefjorden)",
      "Account": "Inventory Pakke (Sognefjorden)",
      "Action": "Search",
      "Duration": "00:00:00.1982185",
      "Success": true,
      "ErrorMessage": null
    }
  ]
}
```

This is a **POST** request that requires a filter with some mandatory properties, such as the start and end dates of the calendar, the pointOfSalesId and the currency. 
As in other transport queries, the filter can also include a content filter, such as only those transport products associated with a particular CBIS category or with certain attributes. 
As there is no paging for the calendar content search it is sensible to request the bare minimum both in terms of products searched and content returned.
Content possibilities can be found in the <a href="#content-filter">Content Section</a> You can see a bare minimum version of this search in the examples.
The return of this call is transport products that have availabilities within the time range you are looking for, instead of occasions and quotes you simply get a list of days the product is available.
 
### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/availability/transport/calendar/byproduct`

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
  "PromoCode": "string" // string - Optional
}
</code>
