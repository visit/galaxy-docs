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
  "Fees": [
    {
      "Currency": "SEK",
      "Price": 50.0,
      "Vat": 10.0,
      "Terms": null,
      "Name": "Service fee",
      "Date": "2017-09-27T13:12:54.1938577Z",
      "Status": "New"
    }
  ],
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
          "Price": 1200.0,
          "ProductVat": 128.57,
          "ExternalBookingCode": "16215808",
          "Addons": [
            {
              "Id": 4,
              "Name": "Frukost",
              "Price": 0.0,
              "PriceIncluded": true,
              "ProductVat": 0.0,
              "CBISProductId": null,
              "ProductTypeId": 1192890,
              "LineType": "Included",
              "Quantity": 2,
              "Currency": "SEK",
              "GrossAmount": 200.00,
              "NetAmount": 178.57,
              "VatAmount": 21.43,
              "VatPercent": 12.0,
              "VatBreakdown": [
                {
                  "VatPercent": 12.0,
                  "GrossAmount": 200.00,
                  "NetAmount": 178.57,
                  "VatAmount": 21.43,
                  "DiscountedGrossAmount": 180.00,
                  "DiscountedNetAmount": 160.71,
                  "DiscountedVatAmount": 19.29
                }
              ],
              "DiscountedGrossAmount": 180.00,
              "DiscountedNetAmount": 160.71,
              "DiscountedVatAmount": 19.29
            }
          ],
          "CBISProductId": "cbis:123456",
          "GrossAmountExcludingAddons": 1000.00,
          "NetAmountExcludingAddons": 892.86,
          "VatAmountExcludingAddons": 107.14,
          "VatPercent": 12.0,
          "VatBreakdown": [
            {
              "VatPercent": 12.0,
              "GrossAmount": 1000.00,
              "NetAmount": 892.86,
              "VatAmount": 107.14,
              "DiscountedGrossAmount": 900.00,
              "DiscountedNetAmount": 803.57,
              "DiscountedVatAmount": 96.43
            }
          ],
          "DiscountedGrossAmountExcludingAddons": 900.00,
          "DiscountedNetAmountExcludingAddons": 803.57,
          "DiscountedVatAmountExcludingAddons": 96.43
        }
      ],
      "Id": 153663,
      "Name": "BookVisit Hotel",
      "CBISProductId": null
    }
  ],
  "Currency": "SEK",
  "PointOfSalesId": 1234,
  "TotalGrossAmount": 1130.00,
  "TotalNetAmount": 1004.28,
  "TotalVatAmount": 125.72
}
```

Gets all the information about a booking by version. The example is a double room with an included breakfast, booked with a 10% discount, plus a service fee.


### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/reservation/version`

### Query Parameters

Parameter | Description
--------- | -----------
reservationVersionId | The Id for the specific version of the Reservation

### Amounts and VAT

Every product and addon has its own amount, VAT and VAT rate, so each line can be booked on its own in your accounting. `Price` and `ProductVat` are unchanged: a product's `Price` also holds its included addons, and an included addon's `Price` is 0.

Field | Description
--------- | -----------
GrossAmountExcludingAddons | The product's own amount including VAT, without its addons, before the booking's discount. This plus the `GrossAmount` of every included addon is the product's `Price`
NetAmountExcludingAddons | `GrossAmountExcludingAddons` minus `VatAmountExcludingAddons`
VatAmountExcludingAddons | The VAT of `GrossAmountExcludingAddons`
Addons.GrossAmount | The addon's own amount including VAT, before the booking's discount. Set for an included addon too. For any other addon it is the addon's `Price`
Addons.NetAmount | `GrossAmount` minus `VatAmount`
Addons.VatAmount | The VAT of `GrossAmount`
VatPercent | The VAT rate in percent (25 is 25%). Null when the line has several rates or the rate is unknown
VatBreakdown | The line's amounts per VAT rate, for lines with several rates such as a ticket bundle with 6% and 25%
Discounted... | The same amounts after the booking's discount, as the invoice charges them. Null when the line has no discount
Addons.LineType | `Included`, `Mandatory`, `Optional`, `ExtraBed` or `Unknown`
Addons.Quantity | The number of units booked
Addons.ProductTypeId | The Citybreak product type of the addon, set even when it has no CBIS product
TotalGrossAmount | What the booking costs after its discount: every line's discounted gross amount (its gross amount when the line has no discount) plus the fees that are not removed
TotalNetAmount | `TotalGrossAmount` minus `TotalVatAmount`
TotalVatAmount | The booking's VAT after its discount: every line's discounted VAT (its VAT when the line has no discount) plus the VAT of the same fees

To add up the lines yourself, take each line's `Discounted...` amount when it is set, and its amount before the discount when it is null. All amounts are rounded to 2 decimals before they are added up, so each total is exactly the sum of the returned values. `Fees` lists the booking fees and cancellation insurance with their price and VAT; fees are never discounted.

<aside class="notice">The amounts are those of your own organization: what it sells each line for, or when it sells nothing on the line, what it buys it for. When the customer pays the supplier directly and your organization only earns a commission, they are what the customer pays. When the amounts do not add up to the booking's prices, that product's amounts and the booking's totals are null rather than contradicting the prices.</aside>





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
  "Fees": [
    {
      "Currency": "SEK",
      "Price": 50.0,
      "Vat": 10.0,
      "Terms": null,
      "Name": "Service fee",
      "Date": "2017-09-27T13:12:54.1938577Z",
      "Status": "New"
    }
  ],
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
          "Price": 1200.0,
          "ProductVat": 128.57,
          "ExternalBookingCode": "16215808",
          "Addons": [
            {
              "Id": 4,
              "Name": "Frukost",
              "Price": 0.0,
              "PriceIncluded": true,
              "ProductVat": 0.0,
              "CBISProductId": null,
              "ProductTypeId": 1192890,
              "LineType": "Included",
              "Quantity": 2,
              "Currency": "SEK",
              "GrossAmount": 200.00,
              "NetAmount": 178.57,
              "VatAmount": 21.43,
              "VatPercent": 12.0,
              "VatBreakdown": [
                {
                  "VatPercent": 12.0,
                  "GrossAmount": 200.00,
                  "NetAmount": 178.57,
                  "VatAmount": 21.43,
                  "DiscountedGrossAmount": 180.00,
                  "DiscountedNetAmount": 160.71,
                  "DiscountedVatAmount": 19.29
                }
              ],
              "DiscountedGrossAmount": 180.00,
              "DiscountedNetAmount": 160.71,
              "DiscountedVatAmount": 19.29
            }
          ],
          "CBISProductId": "cbis:123456",
          "GrossAmountExcludingAddons": 1000.00,
          "NetAmountExcludingAddons": 892.86,
          "VatAmountExcludingAddons": 107.14,
          "VatPercent": 12.0,
          "VatBreakdown": [
            {
              "VatPercent": 12.0,
              "GrossAmount": 1000.00,
              "NetAmount": 892.86,
              "VatAmount": 107.14,
              "DiscountedGrossAmount": 900.00,
              "DiscountedNetAmount": 803.57,
              "DiscountedVatAmount": 96.43
            }
          ],
          "DiscountedGrossAmountExcludingAddons": 900.00,
          "DiscountedNetAmountExcludingAddons": 803.57,
          "DiscountedVatAmountExcludingAddons": 96.43
        }
      ],
      "Id": 153663,
      "Name": "BookVisit Hotel",
      "CBISProductId": null
    }
  ],
  "Currency": "SEK",
  "PointOfSalesId": 1234,
  "TotalGrossAmount": 1130.00,
  "TotalNetAmount": 1004.28,
  "TotalVatAmount": 125.72
}
```

Gets all the information about the latest version of a booking. The amounts are described under <a href="#amounts-and-vat">Amounts and VAT</a>.


### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/reservation/latest`

### Query Parameters

Parameter | Description
--------- | -----------
BookingCode | The code representing the reservation returned from <a href="#commit-status">Commit Status</a> 






## Get Cancellation Cost

```shell
curl -X GET
--header 'Accept: application/json'
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept-Language: en-US'
'https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}",
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
  "BookingCode": "EWOK12",
  "Currency": "SEK",
  "MayRemoveCancellationFees": true,
  "TotalCancellationCost": 1255.0,
  "TotalIfCancellationFeesRemoved": 105.0,
  "Fees": [
    {
      "Name": "Service fee",
      "Type": "BookingFee",
      "Amount": 105.0
    },
    {
      "Name": "Cancellation fee",
      "Type": "CancellationFee",
      "Amount": 1150.0
    }
  ]
}
```

Shows what cancelling the latest version of a reservation would charge if you cancelled it now, and whether you may waive the cancellation fees. Nothing is cancelled, locked or charged, so you can call this before you <a href="#cancel-reservation">Cancel Reservation</a>.

`TotalCancellationCost` is the sum of `Fees`. Fees of type `CancellationFee` come from the cancellation rules, and they are the fees that `RemoveCancellationFees` waives. Fees of any other type are charged either way, for example a `BookingFee` that the operator keeps after a cancellation. `TotalIfCancellationFeesRemoved` is what you would still be charged with the cancellation fees waived.

Cancellation insurance on the reservation is listed in `Fees` as well, with type `CancellationInsurance` or `ExternalCancellationInsurance`. It is charged either way, like the other fees that are not of type `CancellationFee`.

`MayRemoveCancellationFees` is always `true` when your organization is the operator that sold the reservation. When you book as an agent, it is `true` only if the operator has allowed you to waive cancellation fees on your agent business relationship in Citybreak.

<aside class="notice">The amounts apply at the moment of the call and are not a quote. The cancellation rules are matched against the time you cancel, so cancelling later, or after the reservation has been changed, can charge something else.</aside>

If there is no reservation with that booking code that your API key can see, the call returns 404.

### HTTP Request

`GET https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}`

### Query Parameters

Parameter | Description
--------- | -----------
BookingCode | The code representing the reservation returned from <a href="#commit-status">Commit Status</a>
Accept-Language | The language culture (e.g en-us)






## Cancel Reservation

```shell
curl -X POST
--header 'Accept: application/json'
--header 'Content-Type: application/json'
--header 'apiKey: APIKEY132456789EWOK'
--header 'Accept-Language: en-US' -d '{
  "RemoveCancellationFees": true,
  "CancellationReason": "Waived as agreed with the operator"
}' 'https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}",
{
  method: "POST",
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US",
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    "RemoveCancellationFees": true,
    "CancellationReason": "Waived as agreed with the operator"
  })
});
```

> Example of response: int32

This will cancel a reservation. Similarly to committing a Basket, it returns an integer. Use this value in <a href="#commit-status">Commit Status</a> to see the status of your cancel job

The body is optional. Without it the reservation is cancelled and the fees shown by <a href="#get-cancellation-cost">Get Cancellation Cost</a> are charged. Set `RemoveCancellationFees` to cancel without charging the cancellation fees. This needs `MayRemoveCancellationFees` to be `true`; otherwise the call returns 403 and nothing is cancelled.

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/reservation/cancel/{bookingCode}`

### Query Parameters

Parameter | Description
--------- | -----------
BookingCode | The code representing the reservation returned from <a href="#commit-status">Commit Status</a> 
Accept-Language |	The language culture (e.g en-us)

### Body Parameters

Parameter | Description
--------- | -----------
RemoveCancellationFees | Optional. `true` cancels without charging the fees of type `CancellationFee`. Fees of other types are still charged.
CancellationReason | Optional. A note for the operator, saved on the reservation as its internal comment.






## Load Reservation to Basket for Edit

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v5/api/reservation/edit/{bookingCode}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/reservation/edit/{bookingCode}",
{
  headers: {
    "ApiKey": "APIKEY132456789EWOK",
    "Accept": "application/json",
	"Accept-Language": "en-US"
  }  
});
```

> Example of response: int32

Loads reservation to basket and returns basket id. Use this basket id to add or remove products.
Most amendments scenarios require a new booking version. This means that you need to delete the product and add a new product to the booking to get a new booking version.
If you want to replace product with reusing capacity you can add basket id and basket product id to the search query.
If you have loaded a basket/reservation and don’t close it by doing a new commit you need to delete the basket to open it again.


### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/reservation/edit/{bookingCode}`

### Query Parameters

Parameter | Description
--------- | -----------
BookingCode | The code representing the reservation returned from <a href="#commit-status">Commit Status</a> 
Accept-Language |	The language culture (e.g en-us)
