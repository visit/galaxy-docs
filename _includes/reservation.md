# Reservation

**Reservation** calls provide information on, and the ability to cancel, bookings that have been commited. The `BookingCode` is a universal reference for a reservation while the `ReservationVersionId` will show you the different versions of the booking if things have been changed

**GET** and **POST** operations 

## Get Reservation

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/reservation/{bookingCode}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/reservation/{bookingCode}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json"
  }  
});
```

> Example of response:

```json
[
  {
    "BookingCode": "EWOK12",
    "ReservationVersionId": 1234567,
    "Version": 1,
    "Created": "2017-09-27T13:12:54.1938577Z"
  },
  {
    "BookingCode": "EWOK12",
    "ReservationVersionId": 1234568,
    "Version": 2,
    "Created": "2017-09-27T13:14:54.4237553Z"
  }
]
```

Gets all the versions of a booking that have been created with a Booking Code


### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/reservation`

### Query Parameters

Parameter | Description
--------- | -----------
BookingCode | The code representing the reservation returned from <a href="#commit-status">Commit Status</a> 





## Get Reservation Version

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/reservation/version/{reservationVersionId}}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/reservation/version/{reservationVersionId}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json"
  }  
});
```

> Example of response:

```json
{
  "BookingCode": "EWOK12",
  "Version": 1,
  "BookingDate": "2017-09-27T13:12:54.1938577Z",
  "AutoCancellation": "9999-12-31T23:59:59.9999999",
  "Fees": [],
  "BookingUser": {
    "Id": 113685,
    "NameFirst": "Galaxy",
    "NameLast": "Api user",
    "Email": null
  },
  "CancellationMessage": null,
  "LastCancellation": "2017-10-05T15:48:05.997Z",
  "Customer": {
    "NameFirst": "Test",
    "NameLast": "User",
    "Salutation": null,
    "CustomerNumber": null,
    "CustomerType": 0,
    "Culture": null,
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
    "Email": null,
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
  },
  "ProductGroups": [
    {
      "Products": [
        {
          "Id": 3,
          "Name": "Dubbelrum",
          "Price": 350,
          "ExternalBookingCode": "16215808"
        }
      ],
      "Id": 153663,
      "Name": "BookVisit Hotel"
    }
  ]
}
```

Gets all the information about a booking by version


### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/reservation/version`

### Query Parameters

Parameter | Description
--------- | -----------
reservationVersionId | The Id for the specific version of the Reservation





## Get Latest Reservation Version

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/reservation/latest/{bookingCode}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/reservation/latest/{bookingCode}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json"
  }  
});
```

> Example of response:

```json
{
  "BookingCode": "EWOK12",
  "Version": 1,
  "BookingDate": "2017-09-27T13:12:54.1938577Z",
  "AutoCancellation": "9999-12-31T23:59:59.9999999",
  "Fees": [],
  "BookingUser": {
    "Id": 113685,
    "NameFirst": "Galaxy",
    "NameLast": "Api user",
    "Email": null
  },
  "CancellationMessage": null,
  "LastCancellation": "2017-10-05T15:48:05.997Z",
  "Customer": {
    "NameFirst": "Test",
    "NameLast": "User",
    "Salutation": null,
    "CustomerNumber": null,
    "CustomerType": 0,
    "Culture": null,
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
    "Email": null,
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
  },
  "ProductGroups": [
    {
      "Products": [
        {
          "Id": 3,
          "Name": "Dubbelrum",
          "Price": 350,
          "ExternalBookingCode": "16215808"
        }
      ],
      "Id": 153663,
      "Name": "BookVisit Hotel"
    }
  ]
}
```

Gets all the information about a booking by version


### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/reservation/latest`

### Query Parameters

Parameter | Description
--------- | -----------
BookingCode | The code representing the reservation returned from <a href="#commit-status">Commit Status</a> 






## Cancel Reservation

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}",
{
  method: "POST",
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
  }  
});
```

> Example of response: int32

This will cancel a reservation. Similarly to committing a Basket, it returns an integer. Use this value in <a href="#commit-status">Commit Status</a> to see the status of your cancel job

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}`

### Query Parameters

Parameter | Description
--------- | -----------
BookingCode | The code representing the reservation returned from <a href="#commit-status">Commit Status</a> 
Accept-Language |	The language culture (e.g en-us)
