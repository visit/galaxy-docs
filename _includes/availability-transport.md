# Availability - Transport

**Availability - Transport** calls provide information about the availability of any type of transport products. The search will return products with availability, including content, pricing groups, as well as a Search ID with its Expiry. 

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
  "PointOfSalesId": 18724,
  "Currency": "EUR",
  "PageSize": 20,
  "Page": 0,
  "Persons": [
    {
      "Code": "997",
      "Quantity": 2
    }
  ],
  "Vehicles": [],
  "Routes": [
    {
      "DepartureLocationCode": "25142",
      "DepartureDate": "2020-08-21",
      "ArrivalLocationCode": "25132"
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
        "PointOfSalesId": 18724,
        "Currency": "EUR",
        "PageSize": 20,
        "Page": 0,
        "Persons": [
            {
            "Code": "997",
            "Quantity": 2
            }
        ],
        "Vehicles": [],
        "Routes": [
            {
            "DepartureLocationCode": "25142",
            "DepartureDate": "2020-08-21",
            "ArrivalLocationCode": "25132"
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
    "Currency": "EUR",
    "PageSize": 20,
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
    "Vehicles": [],
    "Routes": [
      {
        "DepartureLocationCode": "25142",
        "DepartureDate": "2020-08-21T00:00:00",
        "ArrivalLocationCode": "25132"
      }
    ]
  },
  "Locations": [
    {
      "Code": "25142",
      "City": null,
      "Country": null,
      "Name": "Oslo",
      "Position": null,
      "State": null,
      "Regions": null
    },
    {
      "Code": "25132",
      "City": null,
      "Country": null,
      "Name": "Copenhagen",
      "Position": null,
      "State": null,
      "Regions": null
    }
  ],
  "Fares": [
    {
      "Code": "TOSC",
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
      "Code": "B3",
      "Name": "3-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B3.jpg",
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
            "Value": "3-bed inside cabin with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "3-Bed inside cabin with bunk beds"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "I2",
      "Name": "2-bed inside disabled cabin",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/I2.jpg",
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
            "Value": "2-bed inside disabled cabin"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "BL",
      "Name": "2-bed inside cabin with lower beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/BL.jpg",
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
            "Value": "2-bed inside cabin with lower beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "2-Bed inside cabin with lower beds"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "B4",
      "Name": "4-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B4.jpg",
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
            "Value": "4-bed inside cabin with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Cabin with 2 to 4 beds / bunks\r\n• Bathroom and toilet\r\n• Located from deck 5 and further up the ship."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "B5",
      "Name": "5-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B5.jpg",
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
            "Value": "5-bed inside cabin with bunk beds"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "H2",
      "Name": "2-bed disabled sea view cabin",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/H2.jpg",
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
            "Value": "2-bed disabled sea view cabin"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "AL",
      "Name": "2-bed sea view with lower beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/AL.jpg",
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
            "Value": "2-bed sea view with lower beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Standard Cabin with windows\r\n• For 1-2 people\r\n• 2 beds on the floor\r\n• Toilet and shower\r\n• Bed linen and towels are included in all cabins"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "F4",
      "Name": "4-bed sea view, pet friendly",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/F4.jpg",
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
            "Value": "4-bed sea view, pet friendly"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "A4",
      "Name": "4-bed sea view with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/A4.jpg",
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
            "Value": "4-bed sea view with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Cabin with sea view with 4 beds including en suite bathroom with shower, toilet, wardrobe, bedside table and air conditioning."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "C2",
      "Name": "2-share Commodore cabin",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/C2.jpg",
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
            "Value": "2-share Commodore cabin"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "X2",
      "Name": "2-bed Commodore De Luxe",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/X2.jpg",
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
            "Value": "2-bed Commodore De Luxe"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Commodore Deluxe double bed\r\n• Bed linen and towels\r\n• Cabinet\r\n• Shower/toilet room\r\n• TV\r\n• Clothes hanger\r\n• Mirror\r\n• Hair dryer\r\n\r\nThese cabins have 1 double bed and are usually arranged at the bow, so you can enjoy magnificent sea views throughout your trip."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "O2",
      "Name": "2-bed Owners Suite",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/O2.jpg",
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
            "Value": "2-bed Owners Suite"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "P2",
      "Name": "2-bed Commodore De Luxe with private balcony",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/P2.jpg",
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
            "Value": "2-bed Commodore De Luxe with private balcony"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "O3",
      "Name": "3-bed Owners Suite",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/O3.jpg",
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
            "Value": "3-bed Owners Suite"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "P3",
      "Name": "3-bed Commodore with balcony",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/P3.jpg",
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
            "Value": "3-bed Commodore with balcony"
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
  "Results": [
    {
      "BookKey": "922217350-T",
      "Price": {
        "Price": 57,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1437189711-T",
      "Price": {
        "Price": 64,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B3",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1320630332-T",
      "Price": {
        "Price": 70,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "I2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "953089120-T",
      "Price": {
        "Price": 70,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "BL",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "590026928-T",
      "Price": {
        "Price": 70,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B4",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "875325375-T",
      "Price": {
        "Price": 77,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B5",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1971080184-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "H2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "574664991-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "AL",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1670510337-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "F4",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "738814404-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "A4",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1447031156-T",
      "Price": {
        "Price": 141,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "C2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "348889565-T",
      "Price": {
        "Price": 194,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "X2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "742285496-T",
      "Price": {
        "Price": 233,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "O2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "169329926-T",
      "Price": {
        "Price": 233,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "P2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1415934778-T",
      "Price": {
        "Price": 240,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "O3",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "239820248-T",
      "Price": {
        "Price": 240,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "P3",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    }
  ],
  "SearchId": "af968f68-3067-49c2-b934-ec56b72aed97",
  "ExpirationDate": "2020-07-21T13:11:46.0769699+02:00",
  "TotalResults": 16,
  "Operations": [
    {
      "System": "FerryGateway DFDS",
      "Account": "Ferry Gateway DFDS test",
      "Action": "Search",
      "Duration": "00:00:05.9061986",
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
  "SearchId": "af968f68-3067-49c2-b934-ec56b72aed97"
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
    "SearchId": "af968f68-3067-49c2-b934-ec56b72aed97"
  })  
});
```

> Example of response:

```json
{
  "TransportSearch": {
    "PointOfSalesId": 18724,
    "Currency": "EUR",
    "PageSize": 20,
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
    "Vehicles": [],
    "Routes": [
      {
        "DepartureLocationCode": "25142",
        "DepartureDate": "2020-08-21T00:00:00",
        "ArrivalLocationCode": "25132"
      }
    ]
  },
  "Locations": [
    {
      "Code": "25142",
      "City": null,
      "Country": null,
      "Name": "Oslo",
      "Position": null,
      "State": null,
      "Regions": null
    },
    {
      "Code": "25132",
      "City": null,
      "Country": null,
      "Name": "Copenhagen",
      "Position": null,
      "State": null,
      "Regions": null
    }
  ],
  "Fares": [
    {
      "Code": "TOSC",
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
      "Code": "B3",
      "Name": "3-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B3.jpg",
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
            "Value": "3-bed inside cabin with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "3-Bed inside cabin with bunk beds"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "I2",
      "Name": "2-bed inside disabled cabin",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/I2.jpg",
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
            "Value": "2-bed inside disabled cabin"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "BL",
      "Name": "2-bed inside cabin with lower beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/BL.jpg",
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
            "Value": "2-bed inside cabin with lower beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "2-Bed inside cabin with lower beds"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "B4",
      "Name": "4-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B4.jpg",
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
            "Value": "4-bed inside cabin with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Cabin with 2 to 4 beds / bunks\r\n• Bathroom and toilet\r\n• Located from deck 5 and further up the ship."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "B5",
      "Name": "5-bed inside cabin with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/B5.jpg",
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
            "Value": "5-bed inside cabin with bunk beds"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "H2",
      "Name": "2-bed disabled sea view cabin",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/H2.jpg",
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
            "Value": "2-bed disabled sea view cabin"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "AL",
      "Name": "2-bed sea view with lower beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/AL.jpg",
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
            "Value": "2-bed sea view with lower beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Standard Cabin with windows\r\n• For 1-2 people\r\n• 2 beds on the floor\r\n• Toilet and shower\r\n• Bed linen and towels are included in all cabins"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "F4",
      "Name": "4-bed sea view, pet friendly",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/F4.jpg",
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
            "Value": "4-bed sea view, pet friendly"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "A4",
      "Name": "4-bed sea view with bunk beds",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/A4.jpg",
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
            "Value": "4-bed sea view with bunk beds"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "Cabin with sea view with 4 beds including en suite bathroom with shower, toilet, wardrobe, bedside table and air conditioning."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "C2",
      "Name": "2-share Commodore cabin",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/C2.jpg",
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
            "Value": "2-share Commodore cabin"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "X2",
      "Name": "2-bed Commodore De Luxe",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/X2.jpg",
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
            "Value": "2-bed Commodore De Luxe"
          },
          {
            "Id": 102,
            "Name": "Description",
            "Value": "• Commodore Deluxe double bed\r\n• Bed linen and towels\r\n• Cabinet\r\n• Shower/toilet room\r\n• TV\r\n• Clothes hanger\r\n• Mirror\r\n• Hair dryer\r\n\r\nThese cabins have 1 double bed and are usually arranged at the bow, so you can enjoy magnificent sea views throughout your trip."
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "O2",
      "Name": "2-bed Owners Suite",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/O2.jpg",
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
            "Value": "2-bed Owners Suite"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "P2",
      "Name": "2-bed Commodore De Luxe with private balcony",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/P2.jpg",
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
            "Value": "2-bed Commodore De Luxe with private balcony"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "O3",
      "Name": "3-bed Owners Suite",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/O3.jpg",
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
            "Value": "3-bed Owners Suite"
          }
        ],
        "Categories": null,
        "Geos": null,
        "Pois": null,
        "Position": null
      }
    },
    {
      "Code": "P3",
      "Name": "3-bed Commodore with balcony",
      "Content": {
        "Images": [
          {
            "Uri": "//resources.citybreak.com/online3/img/ferry/DFDS/P3.jpg",
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
            "Value": "3-bed Commodore with balcony"
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
  "Results": [
    {
      "BookKey": "183371946-T",
      "Price": {
        "Price": 57,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "486772987-T",
      "Price": {
        "Price": 64,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B3",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "880669076-T",
      "Price": {
        "Price": 70,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "I2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "256404049-T",
      "Price": {
        "Price": 70,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "BL",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "436437368-T",
      "Price": {
        "Price": 70,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B4",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "32577107-T",
      "Price": {
        "Price": 77,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "B5",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "232531367-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "H2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1317515621-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "AL",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1048363413-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "F4",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "1884085344-T",
      "Price": {
        "Price": 97,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "A4",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "44085498-T",
      "Price": {
        "Price": 141,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "C2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "587097738-T",
      "Price": {
        "Price": 194,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "X2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "708832957-T",
      "Price": {
        "Price": 233,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "O2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "446986406-T",
      "Price": {
        "Price": 233,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "P2",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "670772904-T",
      "Price": {
        "Price": 240,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "O3",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    },
    {
      "BookKey": "745216778-T",
      "Price": {
        "Price": 240,
        "Currency": "EUR"
      },
      "OutboundJourney": {
        "Duration": "17:15:00",
        "CabinCode": "P3",
        "Legs": [
          {
            "DepartureLocationCode": "25142",
            "DepartureTime": "2020-08-21T16:30:00",
            "ArrivalLocationCode": "25132",
            "ArrivalTime": "2020-08-22T09:45:00",
            "Duration": "17:15:00",
            "OperatingCarrierCode": "DFDS",
            "VehicleCode": null,
            "TransportNumber": "NOOSL"
          }
        ],
        "FareCode": "TOSC"
      },
      "HomeboundJourney": null
    }
  ],
  "SearchId": "a04a05dc-5ed9-48c3-8c91-11b6747c4e3f",
  "ExpirationDate": "2020-07-21T14:16:18.7041371+02:00",
  "TotalResults": 16,
  "Operations": [
    {
      "System": "FerryGateway DFDS",
      "Account": "Ferry Gateway DFDS test",
      "Action": "Search",
      "Duration": "00:00:06.0823252",
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
