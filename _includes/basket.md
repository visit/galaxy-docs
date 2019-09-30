# Basket

**Basket** calls are the most complicated in the API workflow as they encapsulate the booking process in typical "shopping basket" object that can have many operations performed on it and which has a limited life span, connected as it is to availability/bookability of products, both internal to Citybreak and from external inventories. It is NOT a reservation but products in a basket are "held" for 60 mins from the time of the <a href="#availability---accommodation">Accommodation</a> or <a href="#availability---activity">Activity</a> Availability Search where possible (i.e. where external inventories allow).

<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the `pointOfSalesId`</aside>




## Create Basket

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' -d '{
  "PointOfSalesId": 1234570,
  "Currency": "SEK"
}' 'https://galaxy.citybreak.com/v4/api/basket/create'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/create",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  },
  body: JSON.Stringify({
    "PointOfSalesId": 1234570,
    "Currency": "SEK"
  })
});
```

> Example of response:

```json
{
  "BasketId": 12345678,
  "Success": true
}
```

Create a new basket object, you'll need to preserve this ID in order to process further operations on the basket.

### HTTP Request

`POST https://galaxy.citybreak.com/v4/api/basket/create`

### Parameters

Parameter | Description
--------- | -----------
PointOfSalesId | The point of sales identifier.
Currency | The currency of the basket




## Create Basket for hybrid checkout in Citybreak Online3

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' -d '{
  "PointOfSalesId": 1234570,
  "Currency": "SEK",
  "Online3Session": {
    "Id": "abcdefg12345678,
    "OnlineId": 123456789
  }
}' 'https://galaxy.citybreak.com/v4/api/basket/create'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/create",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  },
  body: JSON.Stringify({
  "PointOfSalesId": 1234570,
  "Currency": "SEK",
  "Online3Session": {
    "Id": "abcdefg12345678,
    "OnlineId": 123456789
	}
  })
});
```

> Example of response:

```json
{
  "BasketId": 12345678,
  "Success": true
}
```

This alternative way to create a basket is used when you intend to link the customer basket to a Citybreak Online3 guide for customer details & payments

### HTTP Request

`POST https://galaxy.citybreak.com/v4/api/basket/create`

### Parameters

Parameter | Description
--------- | -----------
PointOfSalesId | The point of sales identifier.
Currency | The currency of the basket.
Online3Session.Id | The user session identifier.
Online3Session.OnlineId | The online3 identifier.




## Delete Basket

```shell
curl -X DELETE 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/delete/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/delete/{basketId}",
{
  method:"DELETE"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
true
```

Delete a basket. This will remove all associated information attached to the basket as well.

### HTTP Request

`DELETE https://galaxy.citybreak.com/v4/api/basket/delete/{basketId}`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket to delete.







## Get Basket

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/{basketId}",
{
  method:"GET"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "BasketId": 48869100,
  "Groups": [
    {
      "Id": 1136433,
      "Name": "BookVisit Hotel",
      "Content": {
        "PriceFrom": 0,
        "Images": [
          {
            "Uri": "//images.citybreak.com/image.aspx?ImageId=101010101010",
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
      "Products": [
        {
          "BookItemId": 8,
          "Addons": [
            {
              "AddonId": "A:0-C:0-P:0",
              "NoUnits": 1,
              "IsExtraBed": false,
              "Name": null,
              "IsDeletable": false,
              "Price": {
                "Price": 150
                "Currency": "SEK"
              },
			  "PriceGroupName": "Adult"
            }
          ],
          "Persons": [
            {
              "Name": "Adult",
              "No": 1
            },
            {
              "Name": "Child 0-11",
              "No": 1
            }
          ],
          "Guests": [
            {
              "GuestLinkId": 6,
              "PriceGroupName": "Adult",
              "Guest": {
                "GuestId": 1,
                "NameFirst": "Test",
                "NameLast": "User",
                "Age": 35,
                "Sex": "F",
                "Salutation": "Ms"
              }
            },
            {
              "GuestLinkId": 7,
              "PriceGroupName": "Child 0-11",
              "Guest": {
                "GuestId": 2,
                "NameFirst": null,
                "NameLast": null,
                "Age": 0,
                "Sex": null,
                "Salutation": null
              }
            }
          ],
          "NoUnits": 1,
          "StartDate": "2017-10-14T00:00:00Z",
          "EndDate": "2017-10-15T00:00:00Z",
          "Content": {
            "PriceFrom": null,
            "Images": [
              {
                "Uri": null,
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
                "Value": "Dubbelrum"
              }
            ],
            "Categories": null,
            "Geos": null,
            "Pois": null,
            "Position": null
          },
          "Name": "Dubbelrum",
          "IsDeletable": true,
          "Price": {
            "Price": 350,
            "Currency": "SEK"
          }
        }
      ],
      "Price": {
        "Price": 500,
        "Currency": "SEK"
      },
      "Position": null
    }
  ],
  "OkToBook": true,
  "TotalPrice": {
    "Price": 500,
    "Currency": "SEK"
  },
  "PointOfSalesId": 17692,
  "AutoCancellationDate": "9999-12-31T23:59:59.9999999",
  "CancellationInsurrances": []
}
```

Get a basket. This will fetch a Basket along with all associated information attached to the Basket (the example has one booking added to it). This includes the product booked, the total price, possible cancellation insurances (can be added), `OkToBook` which will be checked before the Basket can be committed and `Guest Information` which is a separate entity to the number of people included and is used to track and record customer information (also can be added to the booking item later in the basket process). Of note is the `BookItemId` in the `Products` section, it is used to delete the item from the basket.

### HTTP Request

`GET https://galaxy.citybreak.com/v4/api/basket`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket to get.







## Find basket by session for hybrid checkout in Citybreak Online3

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/findByOnline3Session?pointOfSalesId={pointOfSalesId&online3Session={online3Session}&online3Id={online3Id}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/findByOnline3Session?pointOfSalesId={pointOfSalesId&online3Session={online3Session}&online3Id={online3Id}",
{
  method:"GET"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
48869100
```

In Online3 hybrid checkout setups, this locates an existing basket by an Online3 session id. Returns the basket id, if found.

### HTTP Request

`GET https://galaxy.citybreak.com/v4/api/basket/findByOnline3Session?pointOfSalesId={pointOfSalesId&online3Session={online3Session}&online3Id={online3Id}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
online3Session | The online 3 session.
online3Id | The online 3 guide identifier 


## Add Accommodation Booking Item

```shell
curl -X PUT 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
--header 'Accept-Language: en-us' -d '[
  {
    "BookKey": "1-A",
    "Amount" 2
  }, {
    "BookKey": "2-A",
    "Amount": 1
  }
]' 'https://galaxy.citybreak.com/v4/api/basket/add/accommodation/{basketId}/{searchId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/add/accommodation/{basketId}/{searchId}",
{
  method:"PUT"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  },
  body: JSON.Stringify(
    [
      {
        "BookKey": "1-A",
        "Amount": 1
      }, {
        "BookKey": "2-A",
        "Amount": 2
      }
    ])
});
```

> Example of response:

```json
{
  "Success": true,
  "BookItemIds": [1,2]
}
```

Adds booking items to the basket, you must first have checked for the <a href="#availability---no-placement-accommodation">Accommodation Availability</a> of a property or properties and obtained the search Id and the bookingKey of the products you wish to add to the basket.

`PUT https://galaxy.citybreak.com/v4/api/basket/add/accommodation`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
searchId | The search Id returned by the <a href="#availability---no-placement-accommodation">Accommodation</a> Availability Response
BookKey | The key of the booking item to add to the basket, found in <a href="#availability---no-placement-accommodation">Availability Response</a>
Amount | The amount to book for this item


## Add Placement Accommodation Booking Item

```shell
curl -X PUT 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/add/accommodation/placement/{basketId}/{searchId}/{bookKey}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/add/accommodation/placement/{basketId}/{searchId}/{bookKey}",
{
  method:"PUT"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "Success": true,
  "BookItemIds": [1,2]
}
```

Add a booking item to the basket, you must first have checked for the <a href="#availability---accommodation">Placement Accommodation Availability</a> of a property or properties and obtained the search Id and the bookingKey of the product you wish to add to the basket.

`PUT https://galaxy.citybreak.com/v4/api/basket/add/accommodation/placement`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
searchId | The search Id returned by the <a href="#availability---accommodation">Accommodation</a> or <a href="#availability---activity">Activity</a> Availability Response
bookKey | The key of the booking item (product) to add to the basket, found in the <a href="#availability---accommodation">Accommodation</a> or <a href="#availability---activity">Activity</a> Availability Search


## Add Fuzzy Accommodation Booking Item

```shell
curl -X PUT 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/add/accommodation/fuzzy/{basketId}/{searchId}/{bookId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/add/accommodation/fuzzy/{basketId}/{searchId}/{bookId}",
{
  method:"PUT"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "Success": true,
  "BookItemIds": [1,2]
}
```

Specifically for the Fuzzy search, to add a booking item to the basket you must first have checked for the <a href="#fuzzy-accommodation-search">Fuzzy Availability</a> of a property or properties and obtained the search Id and the `bookId` of the product you wish to add to the basket. NOTE: the bookId is obtained from the `BookableAlternatives` and is a separate entity from the `bookKey` used in the regular basket operation

`PUT https://galaxy.citybreak.com/v4/api/basket/add/accommodation/fuzzy/`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
searchId | The search Id returned by the <a href="#fuzzy-accommodation-search">Availability Response</a>
bookId | The Id of the booking item (product) to add to the basket, found in <a href="#fuzzy-accommodation-search">the Fuzzy Availability Response</a>


## Add Activity Booking Item

```shell
curl -X PUT 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' -d '[
  {
    "BookKey": "1-T",
    "Amount" 2
  }, {
    "BookKey": "2-T",
    "Amount": 1
  }
]' 'https://galaxy.citybreak.com/v4/api/basket/add/activity/{basketId}/{searchId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/add/activity/{basketId}/{searchId}",
{
  method:"PUT"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  },
  body: JSON.Stringify(
    [
      {
        "BookKey": "1-T",
        "Amount": 1
      }, {
        "BookKey": "2-T",
        "Amount": 2
      }
    ])
});
```

> Example of response:

```json
{
  "Success": true,
  "BookItemIds": [1,2]
}
```

Add a booking item to the basket, you must first have checked for the <a href="#availability---activity">Availability</a> of an activity and obtained the search Id and the bookingKey of the product you wish to add to the basket.

`PUT https://galaxy.citybreak.com/v4/api/basket/add/activity`

### Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
searchId | The search Id returned by the <a href="#availability---activity">Availability Response</a>
BookKey | The key of the booking item to add to the basket, found in <a href="#availability---activity">Availability Response</a>
Amount | The amount to book for this item



## Delete Booking Item

```shell
curl -X DELETE 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/deleteItem/{basketId}/{bookItemId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/deleteItem/{basketId}/{bookItemId}",
{
  method:"DELETE"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
true
```

Delete a booking item from the basket. In the <a href="#get-basket">Get Basket</a> response you can find the bookItemId (this is different to the booking key and is specific to the basket)

### HTTP Request

`DELETE https://galaxy.citybreak.com/v4/api/basket/deleteItem`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
bookItemId | The Id of the booking item to delete from the basket 







## Toggle Cancellation Insurance

```shell
curl -X PUT 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/cancellation/{basketId}/{cancellationId}/{true|false}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/cancellation/{basketId}/{cancellationId}/{true|false}",
{
  method:"PUT"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
no content
```

If your basket has a set of cancellation insurances you can use this call to add one (true) or switch it off (false)

### HTTP Request

`PUT https://galaxy.citybreak.com/v4/api/basket/cancellation`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
cancellationId | The Id of the cancellation insurance to toggle
state | true (added) or false (not added)






## Update Customer Information

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept-Language: en-us' -d '{
   "NameFirst": "Test",
   "NameLast": "User",
   "Salutation": "Ms",
   "CustomerType": "Private",
   "Culture": "en-US",
   "Address": { 
     "StreetAddress1": "Test Road 123",
     "PostalCode": "41111",
     "City": "Gothenburg",
     "CountryCode": "SE"
   },
   "Email": "testuser%40visit.com",
   "PhoneMobile": { 
     "CountryCode": "46",
     "AreaCode": "07",
     "Number": "2222222"
   }
 }' 'https://galaxy.citybreak.com/v4/api/basket/customer/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/customer/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
  body: JSON.Stringify({
    "NameFirst": "Test",
    "NameLast": "User",
    "Salutation": "Ms",
    "CustomerType": "Private",
    "Culture": "en-US",
    "Address": {
      "StreetAddress1": "Test Road 123",
      "PostalCode": "41111",
      "City": "Gothenburg",
      "CountryCode": "SE"
    },
    "Email": "testuser@visit.com",
    "PhoneMobile": {
      "CountryCode": "46",
      "AreaCode": "07",
      "Number": "2222222"
    }
  }
}
});
```

> Example of response:

```json
no content
```

To commit a Basket you will need to provide customer information. This is fairly standard: name, address, email. phone, etc. for the person conducting the booking (not necessarily the Guests)

### HTTP Request

`POST https://galaxy.citybreak.com/v4/api/basket/customer`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.






## Get Customer Information

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept-Language: en-US' 
'https://galaxy.citybreak.com/v4/api/basket/customer/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/customer/{basketId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "NameFirst": "Test",
  "NameLast": "User",
  "Salutation": null,
  "CustomerNumber": null,
  "CustomerType": 1,
  "Culture": "en-US",
  "CivicRegistrationNumber": null,
  "Company": null,
  "CompanyDepartment": null,
  "Address": {
    "StreetAddress1": "Test Road 123",
    "StreetAddress2": null,
    "StreetAddress3": null,
    "PostalCode": "41111",
    "City": "Gothenburg",
    "CountryCode": "SE",
    "State": null
  },
  "Email": "testuser@visit.com",
  "PhoneHome": {
    "CountryCode": null,
    "AreaCode": null,
    "Number": null
  },
  "PhoneWork": {
    "CountryCode": null,
    "AreaCode": null,
    "Number": null
  },
  "PhoneMobile": {
    "CountryCode": "46",
    "AreaCode": "07",
    "Number": "2222222"
  }
}
```

Get currencies available for a given Point of Sale. Availability searches will require a currency for a valid search.

### HTTP Request

`GET https://galaxy.citybreak.com/v4/api/basket/customer`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.

## Commit Basket

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-US' 
'https://galaxy.citybreak.com/v4/api/basket/commit/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/commit/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
}  
});
```

> Example of response:

```json
int32
```

This is the method used to start a commit job for a basket. You only need to provide the Basket Id for this call. As there may be many products from different internal and external providers this is essentially a two step async operation. Once you have committed the basket you can query <a href="#commit-status">Commit Status</a> to get the status of the job and the `ReservationID` and `BookingCode` if it is completed. Before you may commit a basket, there is some information you must provide first. Add at least one Booking Item (<a href="#add-accommodation-booking-item">Accommodation</a>, <a href="#add-fuzzy-accommodation-booking-item">Fuzzy Accommodation</a> or <a href="#add-activity-booking-item">Activity</a>) and provide <a href="#update-customer-information">Customer Information</a>.

The return value is a job number with which you can check the status of commit

### HTTP Request

`POST https://galaxy.citybreak.com/v4/api/basket/commit/{basketId}`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.






## Commit Status

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-US'

'https://galaxy.citybreak.com/v4/api/basket/commit/status/{commitJobId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/commit/status/{commitJobId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json"
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
{
  "Status": "CompletedOk",
  "Subtasks": [
    {
      "Task": "StartingCommit",
      "Status": "CompletedOk",
      "ExtraInfo": null
    },
    {
      "Task": "CreatingConfirmations",
      "Status": "CompletedOk",
      "ExtraInfo": null
    },
    {
      "Task": "CreditCardAction",
      "Status": "CompletedOk",
      "ExtraInfo": null
    },
    {
      "Task": "CreatingInvoices",
      "Status": "NotStarted",
      "ExtraInfo": null
    },
    {
      "Task": "CreatingStatistics",
      "Status": "NotStarted",
      "ExtraInfo": null
    },
    {
      "Task": "FinishingTransaction",
      "Status": "CompletedOk",
      "ExtraInfo": null
    }
  ],
  "ResvversionId": 1234567,
  "BookingCode": "EWOK12"
}
```

Gets the `ResvversionId` (reservation version id) and `BookingCode`, important for <a href="#reservation">Reservation</a> calls, and the status of a commit job. Get the commit job id when you make the <a href="#commit-basket">Commit</a>.


### HTTP Request

`GET https://galaxy.citybreak.com/v4/api/basket/commit/status`

### Query Parameters

Parameter | Description
--------- | -----------
commitJobId | The Id of the commit job returned from <a href="#commit-basket">Commit Basket</a> 



## Add Guest

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/guests/add/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/guests/add/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
  body: JSON.Stringify([
    {
      "GuestId": 1,
      "NameFirst": "Test",
      "NameLast": "User",
      "Age": 35,
      "Sex": "F",
      "Salutation": "Ms"
    }
  ]
);
```

Returns Response Code 204 if successful. Add a guest to a Booking Item, this is not the same as Customer Information. The Guest ID in the filter must match one in the <a href="#get-basket">Basket</a> or be 0 to create a new guest

### HTTP Request

`GET https://galaxy.citybreak.com/v4/api/basket/guests/add`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.


## Addon products

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/api/basket/addon/{basketId}/{bookItemId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/api/basket/addon/{basketId}/{bookItemId}",
{
  method:"GET"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }
);
```

> Example of response

```json
{
  "BookItemId": 1,
  "ProductName": "My activity name",
  "AvailableAddons": [
    {
      "Name": "Sparkling wine",
      "AddonId": "A:0-C:0-P:0",
      "PricegroupName": "Adult",
      "MinimumPricegroupAge": 0,
      "MaximumPricegroupAge": 0,
      "Price": {
        "Price": 175,
        "Currency": "NOK"
      },
      "MinimumNumberOfUnits": 0,
      "MaximumNumberOfUnits": 0
    }
  ]
}
```
Once a product is added to the basket, all mandatory included sub products
are also included. 
There may however be addon products that are optional.

These calls allows you to get a list of available addons.
The main product is refered to by its ID in the basket, the `BookItemId`. 
You can get all the addons for a given basket or a given product in a basket.

Addons might be priced by pricegroup, which is indicated by the fields `PricegroupName`, `MinimumPricegroupAge` and `MaximumPricegroupAge`.

The quantity available to book is indicated by the fields `MinimumNumberOfUnits` and `MaximumNumberOfUnits`.

### HTTP Requests

`GET https://galaxy.citybreak.com/v4/api/api/basket/addon/{basketId}/{bookItemId}`  
`GET https://galaxy.citybreak.com/v4/api/api/basket/addon/{basketId}`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
bookItemId | The Id of the booking item on which to operate

## Add addon product

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' -d '{
  "Queries": [
    {
      "BookItemId": 1,
      "AddonId": "A:0-C:0-P:0",
      "Quantity": 2
    }
  ]
}' 'https://galaxy.citybreak.com/v4/api/basket/addon/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/addon/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
  body: JSON.Stringify(
    {
      "Queries": [
      {
        "BookItemId": 1,
        "AddonId": "A:0-C:0-P:0",
        "Quantity": 2
      }
    ]
  }
);
```

The example call will add 2 sparkling wine to the item with `BookItemId` 1. Set the quantity to 0 to remove the addon.

The quantity available to book is indicated by the fields `MinimumNumberOfUnits` and `MaximumNumberOfUnits` from the <a href="#addon-products">Addon products</a> call.

### HTTP Requests

`POST https://galaxy.citybreak.com/v4/api/api/basket/addon/{basketId}`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
Queries | List of addons to add
BookItemId | Id in the basket of the product which should receive the addon
AddonId | Id of the addon to add
Quantity | Amount to book

## Get supplier messages

```shell
curl -X GET 
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/suppliermessage/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/suppliermessage/{basketId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json"
    "Accept-Language": "en-US"
  }  
});
```


> Example of Response

```json
[
    {
        "SupplierName": "HafjellKvitfjell Booking AS - Hytter",
        "SupplierId": 54705,
        "Message": null
    }
]
```

It is possible to send a note to the supplier while acting on the basket.
This call will result in a list of available suppliers and the configured messages.

### HTTP Request

`GET https://galaxy.citybreak.com/v4/api/basket/suppliermessage/{basketId}`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.

## Set supplier messages

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' -d '[
  {
    "SupplierId": 54705,
    "Message": "Will arrive late."
  }
]' 'https://galaxy.citybreak.com/v4/api/basket/suppliermessage/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/suppliermessage/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
  body: JSON.Stringify([
    {
      "SupplierId": 54705,
      "Message": "Will arrive late."
    }
  ]
);
```

Update the messages by posting to the same url
The example will set the message to the supplier. You can update one or more messages
to the suppliers with a single post.

## Update Cancellation Insurance status

```shell
curl -X PUT 
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/cancellation/{basketId}/{insuranceId}/{state}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/cancellation/{basketId}/{insuranceId}/{state}",
{
  method:"PUT"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
);
```

If an cancellation insurance is available, you can find a reference in the basket to it.

<code class="center-column">
    /* parts of the basket */
    "CancellationInsurances": [
        {
            "Name": "Avbestillingsforsikring ",
            "Description": "",
            "Id": 97,
            "CurrentCost": 500,
            "Currency": "NOK",
            "Selected": false,
            "PreSelect": false,
            "CanBeChanged": true,
            "Introduction": "",
            "CancellationInsuranceProducts": []
        }
    ]    
</code>

The state is either `true` or `false`. 

<aside class="notice">
If `CanBeChanged` is false, nothing will happen.
</aside>

The basket price will reflect the new total. 
The insurance is usually based on the types of products that are included in the 
basket right now. It could be fixed per booking, fixed per product or a percentage
of the product cost. Hence the `CurrentCost`.

## Get Complementary Information

```shell
curl -X GET 
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
'https://galaxy.citybreak.com/v4/api/basket/complementary/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/complementary/{basketId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json"
    "Accept-Language": "en-US"
  }  
});
```


> Example of Response

```json
{
  "BasketId": 123456,
  "Products": [
    {
      "ProductName": "Generic Activity",
      "ItemId": "1",
      "ComplementaryInfo": [
        {
          "Code": "#COMP-3",
          "Value": "",
          "Type": "Boolean",
          "IsRequired": true,
          "Label": "Require a guide?",
          "Comment": null,
          "Message": null,
          "Constraints": null
        }
      ],
      "Persons": [
        {
          "ItemId": "db2bca44-e134-4709-b604-61e8baa798f4",
          "ComplementaryInfo": [
            {
              "Code": "#COMP-0",
              "Value": "",
              "Type": "Date",
              "IsRequired": false,
              "Label": "Estimated Arrival Date",
              "Comment": null,
              "Message": null,
              "Constraints": {
                "MaxStringLength": null,
                "MinStringLength": null,
                "MinIntValue": null,
                "MaxIntValue": null,
                "MinDecimalValue": null,
                "MaxDecimalValue": null,
                "MinDateValue": "0001-01-01T00:00:00",
                "MaxDateValue": "9999-12-31T00:00:00",
                "MaxImageHeightInPx": null,
                "MaxImageWidthInPx": null,
                "MaxImageSizeInBytes": null
              }
            }
          ]
        }
      ],
      "AddOns": [
        {
          "AddOnName": "Helmet",
          "ItemId": "2",
          "ComplementaryInfo": [
            {
              "Code": "#COMP-1",
              "Value": "",
              "Type": "Integer",
              "IsRequired": false,
              "Label": "Helmet Size",
              "Comment": null,
              "Message": null,
              "Constraints": {
                "MaxStringLength": null,
                "MinStringLength": null,
                "MinIntValue": 1,
                "MaxIntValue": 20,
                "MinDecimalValue": null,
                "MaxDecimalValue": null,
                "MinDateValue": null,
                "MaxDateValue": null,
                "MaxImageHeightInPx": null,
                "MaxImageWidthInPx": null,
                "MaxImageSizeInBytes": null
              }
            }
          ],
        }
      ]
    }
  ]
}
```

Complementary info for products can be retrieved from a basket. This information is often used for things like arrival dates, the names of participants in an activity or any other information that the activity supplier might require in the booking. 

Complementary info can be required or optional and is typed. Currently supported types are Boolean, Integer, Decimal, String, Date and ImageLink. Complementary info may also come with constraints depending on type. If any update attempts are made to info that conflicts with these type restrictions or constraints they will not be successful.

Each Complement is attached to either the main product, the persons who are attached to the product (this may not refer to any specific person but simply the idea of a participant or guest) or to the add on product. These objects are identified by their `ItemId` (for products and add ons this ItemId is equivalent to the BookItemId in the <a href="#get-basket">Get Basket</a> call), each complementary that is attached to an item will also have a unique `Code` within that context. These two identifiers are important for updating the `Value`


### HTTP Request

`GET https://galaxy.citybreak.com/v4/api/basket/complementary/{basketId}`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.

## Set Complementary Information

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'Accept-Language: en-us' 
--header 'apiKey: APIKEY132456789EWOK' -d '[
  {
    "BookItemId": "f18658ea-6cbd-41cf-b243-30799e3e0598",
    "Code": "#COMP-0",
    "Value": "2019-04-01"
  },
  {
    "BookItemId": "2",
    "Code": "#COMP-1",
    "Value": "1000"
  },
    {
    "BookItemId": "1",
    "Code": "#COMP-3",
    "Value": "This is not a Boolean"
  }
]' 'https://galaxy.citybreak.com/v4/api/basket/complementary/{basketId}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v4/api/basket/complementary/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
  body: JSON.Stringify([
  {
    "BookItemId": "f18658ea-6cbd-41cf-b243-30799e3e0598",
    "Code": "#COMP-0",
    "Value": "2019-04-01"
  },
  {
    "BookItemId": "2",
    "Code": "#COMP-1",
    "Value": "1000"
  },
    {
    "BookItemId": "1",
    "Code": "#COMP-3",
    "Value": "This is not a Boolean"
  }
]
);
```

> Example of Response

```json
[
    {
        "Code": "#COMP-0",
        "ItemId": "f18658ea-6cbd-41cf-b243-30799e3e0598",
        "Success": true,
        "Error": ""
    },
    {
        "Code": "#COMP-1",
        "ItemId": "2",
        "Success": false,
        "Error": "Value - 1000 - must be between 1 and 20"
    },
    {
        "Code": "#COMP-3",
        "ItemId": "1",
        "Success": false,
        "Error": "Value - This is not a Boolean - must be a Boolean"
    }
]

```

When setting complementary information you need the `basketId` of the booking you wish to update and for each complementary, the `ItemId` and `Code`. It is important to take note of the type of the information and if there are any constraints. Valid updates will be made, invalid ones won't. The return type is a list of successful and unsuccessful updates along with a reason why an update failed if `Success` is false. To the right you can see one successful and two unsuccessful updates in the examples.

The update object is fairly simple:

<code class="center-column">
[
  {
    "ItemId": "f18658ea-6cbd-41cf-b243-30799e3e0598",
    "Code": "#COMP-0",
    "Value": "2019-04-01"
  }
]
</code>

### HTTP Request

`POST https://galaxy.citybreak.com/v4/api/basket/complementary/{basketId}`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
list of updates | the POST body with updates
