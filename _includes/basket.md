# Basket

> Basket

**Basket** calls are the most complicated in the API workflow as they encapsulate the booking process in typical "shopping basket" object that can have many operations performed on it and which has a limited life span, connected as it is to availability/bookability of products, both internal to Citybreak and from external inventories. It is NOT a reservation but products in a basket are "held" for 15 mins from the time of the <a href="https://visit.github.io/galaxy-docs/#Availability">Availability Search</a> where possible (i.e. where external inventories allow).

<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the **{pointOfSalesId}**</aside>




## Create Basket

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.test.citybreak.com/v2/api/basket/create/{pointofSalesId}/{currency}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/create/{PointofSalesId}/{Currency}",
{
  method:"POST"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
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

`POST https://galaxy.test.citybreak.com/v2/api/basket/create/{pointofSalesId}/{currency}`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
currency | The currency of the basket




## Delete Basket

```shell
curl -X DELETE 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.test.citybreak.com/v2/api/basket/delete/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/delete/{basketId}",
{
  method:"DELETE"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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

`DELETE https://galaxy.test.citybreak.com/v2/api/basket/delete/{basketId}`

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
'https://galaxy.test.citybreak.com/v2/api/basket/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/{basketId}",
{
  method:"GET"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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
      "Products": [
        {
          "BookItemId": 8,
          "Addons": [
            {
              "Id": 9,
              "NoUnits": 1,
              "IsExtraBed": false,
              "Name": null,
              "IsDeletable": false,
              "Price": {
                "Price": 150,
                "VatAmount": 30,
                "Currency": "SEK"
              }
            }
          ],
          "Persons": [
            {
              "Name": "Vuxen",
              "No": 1
            },
            {
              "Name": "Barn 0-11",
              "No": 1
            }
          ],
          "Guests": [
            {
              "GuestLinkId": 6,
              "PriceGroupName": "Vuxen",
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
              "PriceGroupName": "Barn 0-11",
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
                "Value": "Dubbelrum ÖSD"
              }
            ],
            "Categories": null,
            "Geos": null,
            "Pois": null,
            "Position": null
          },
          "Name": "Dubbelrum ÖSD",
          "IsDeletable": true,
          "Price": {
            "Price": 350,
            "VatAmount": 5.172413793103448,
            "Currency": "SEK"
          }
        }
      ],
      "Price": {
        "Price": 500,
        "VatAmount": 35.172413793103445,
        "Currency": "SEK"
      },
      "Position": null
    }
  ],
  "OkToBook": true,
  "TotalPrice": {
    "Price": 500,
    "VatAmount": 35.172413793103445,
    "Currency": "SEK"
  },
  "PointOfSalesId": 17692,
  "AutoCancellationDate": "9999-12-31T23:59:59.9999999",
  "CancellationInsurrances": []
}
```

Get a basket. This will fetch a Basket along with all associated information attached to the Basket (the example has one booking added to it). This includes the product booked, the total price and VAT, possible cancellation insurances (can be added), **OkToBook** which will be checked before the Basket can be commited and **Guest Information** which is a separate entity to the number of people included and is used to track and record customer information (also can be added to the booking item later in the basket process). Of note is the **BookItemId** in the **Products** section, it is used to delete the item from the basket.

### HTTP Request

`GET https://galaxy.test.citybreak.com/v2/api/basket`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket to get.








## Add Booking Item

```shell
curl -X PUT 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.test.citybreak.com/v2/api/basket/add/accommodation/{basketId}/{searchId}/{bookingKey}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/add/accommodation/{basketId}/{searchId}/{bookingKey}",
{
  method:"PUT"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
true
```

Add a booking item to the basket, you must first have checked for the <a href="https://visit.github.io/galaxy-docs/#Availability">Availability</a> of a property or properties and obtained the search Id and the bookingKey of the product you wish to add to the basket.

`PUT https://galaxy.test.citybreak.com/v2/api/basket/add/accommodation`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
searchId | The search Id returned by the <a href="https://visit.github.io/galaxy-docs/#Availability">Availability Response</a>
bookingKey | The key of the booking item (product) to add to the basket, found in <a href="https://visit.github.io/galaxy-docs/#Availability">Availability Response</a>







## Delete Booking Item

```shell
curl -X DELETE 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.test.citybreak.com/v2/api/basket/deleteItem/{basketId}/{bookItemId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/deleteItem/{basketId}/{bookItemId}",
{
  method:"DELETE"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
});
```

> Example of response:

```json
true
```

Delete a booking item from the basket. In the <a href="https://visit.github.io/galaxy-docs/#get">Get Basket</a> response you can find the bookItemId (this is different to the booking key and is specific to the basket)

### HTTP Request

`DELETE https://galaxy.test.citybreak.com/v2/api/basket/deleteItem`

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
'https://galaxy.test.citybreak.com/v2/api/basket/cancellation/{basketId}/{cancellationId}/{true|false}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/cancellation/{basketId}/{cancellationId}/{true|false}",
{
  method:"PUT"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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

`PUT https://galaxy.test.citybreak.com/v2/api/basket/cancellation`

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
 }' 'https://galaxy.test.citybreak.com/v2/api/basket/customer/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/customer/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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

`GET https://galaxy.test.citybreak.com/v2/api/basket/customer`

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
'https://galaxy.testcitybreak.com/v2/api/basket/customer/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/customer/{basketId}",
{
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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

`GET https://galaxy.test.citybreak.com/v2/api/basket/customer`

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
'https://galaxy.test.citybreak.com/v2/api/basket/commit/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/commit/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
}  
});
```

> Example of response:

```json
int32
```

This is the method used to start a commit job for a basket. You only need to provide the Basket Id for this call. As there may be many products from different internal and external providers this is essentially a two step async operation. Once you have commited the basket you can query <a href="https://visit.github.io/galaxy-docs/#commit-status">Commit Status</a> to get the status of the job and the **ReservationID** and **BookingCode** if it is completed. Before you may commit a basket, there is some information you must provide first. Add at least one <a href="https://visit.github.io/galaxy-docs/#add-booking-item">Booking Item</a> and provide <a href="https://visit.github.io/galaxy-docs/#update-customer-information">Customer Information</a>.

The return value is a job number with which you can check the status of commit

### HTTP Request

`POST https://galaxy.test.citybreak.com/v2/api/basket/commit`

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

'https://galaxy.test.citybreak.com/v2/api/basket/commit/status/{commitJobId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/commit/status/{commitJobId}",
{
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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

Gets the **ResvversionId** (reservation version id) and **BookingCode**, important for <a href="https://visit.github.io/galaxy-docs/#reservation">Reservation</a> calls, and the status of a commit job. Get the commit job id when you make the <a href="https://visit.github.io/galaxy-docs/#commit-basket">Commit</a>.


### HTTP Request

`GET https://galaxy.test.citybreak.com/v2/api/basket/commit/status`

### Query Parameters

Parameter | Description
--------- | -----------
commitJobId | The Id of the commit job returned from <a href="https://visit.github.io/galaxy-docs/#commit-basket">Commit Basket</a> 







## Add Guest

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
--header 'Accept-Language: en-us' 
'https://galaxy.test.citybreak.com/v2/api/basket/guests/add/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/guests/add/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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

> Example of response: no content



Returns Response Code 204 if successful. Add a guest to a Booking Item, this is not the same as Customer Information. The Guest ID in the filter must match one in the <a href="https://visit.github.io/galaxy-docs/#get-basket">Basket</a> or be 0 to create a new guest


### HTTP Request

`GET https://galaxy.test.citybreak.com/v2/api/basket/guests/add`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.


## Optional products

Once a product is added to the basket, all mandatory included sub products
are also included. 
There may however be optional products that needs extra attention.

### HTTP Request

`GET https://galaxy.test.citybreak.com/v2/api/api/basket/optional/{basketId}/{bookItemId}`

```shell
    See javascript example.
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/api/basket/optional/{basketId}/{bookItemId}",
{
  method:"GET"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }
);
```

> It could return something like:

```json
{
    "Product": {
        "BookItemId": 1,
        "ContentId": "pt:444365",
        "Arrival": "2018-04-01T00:00:00",
        "Departure": "2018-04-08T00:00:00",
        "Name": "KRYSTALLEN LEILIGHET A603",
        "Subproducts": [
            {
                "Id": 2,
                "NoUnits": 1,
                "IsExtraBed": false,
                "ProductType": 12,
                "Name": "Sluttvask",
                "IsMandatory": false,
                "Price": { 
                    "Price": 1900,
                    "VatAmount": 228,
                    "Currency": "NOK"
                }
            }
        ],
        "Price": {
            "Price": 21450,
            "VatAmount": 2574,
            "Currency": "NOK"
        }
    },
    "OptionalProducts": [
        {
            "NeedsToSpecifyPricegroups": false,
            "NeedsToSpecifyQuantity": true,
            "Name": "Sengetøy og håndklær",
            "ProducttypeId": 445409,
            "BookedProducts": [
                {
                    "Id": 6,
                    "NoUnits": 1,
                    "IsExtraBed": false,
                    "ProductType": 12,
                    "Name": "Sengetøy og håndklær",
                    "IsMandatory": false,
                    "Price": {
                        "Price": 175,
                        "VatAmount": 43.75,
                        "Currency": "NOK"
                    }
                }
            ],
            "AmountType": "Unlimited",
            "TemplateArguments": {
                "MainProductId": 1,
                "OptionalProducttypeId": 445409,
                "Config": [
                    {
                        "PricegroupName": "Unit",
                        "IsLocalized": false,
                        "Price": {
                            "Price": 175,
                            "VatAmount": 0,
                            "Currency": "NOK"
                        },
                        "PricegroupId": -1,
                        "Quantity": 0
                    }
                ]
            }
        },
        {
            "NeedsToSpecifyPricegroups": false,
            "NeedsToSpecifyQuantity": true,
            "Name": "Vedsekk (sjekk at enheten har ildsted)",
            "ProducttypeId": 456793,
            "BookedProducts": [
                {
                    "Id": 5,
                    "NoUnits": 1,
                    "IsExtraBed": false,
                    "ProductType": 12,
                    "Name": "Vedsekk (sjekk at enheten har ildsted)",
                    "IsMandatory": false,
                    "Price": {
                        "Price": 150,
                        "VatAmount": 37.5,
                        "Currency": "NOK"
                    }
                }
            ],
            "AmountType": "Unlimited",
            "TemplateArguments": {
                "MainProductId": 1,
                "OptionalProducttypeId": 456793,
                "Config": [
                    {
                        "PricegroupName": "Unit",
                        "IsLocalized": false,
                        "Price": {
                            "Price": 150,
                            "VatAmount": 0,
                            "Currency": "NOK"
                        },
                        "PricegroupId": -1,
                        "Quantity": 0
                    }
                ]
            }
        },
        {
            "NeedsToSpecifyPricegroups": false,
            "NeedsToSpecifyQuantity": true,
            "Name": "Barneseng",
            "ProducttypeId": 456758,
            "BookedProducts": [],
            "AmountType": "Unlimited",
            "TemplateArguments": {
                "MainProductId": 1,
                "OptionalProducttypeId": 456758,
                "Config": [
                    {
                        "PricegroupName": "Unit",
                        "IsLocalized": false,
                        "Price": {
                            "Price": 175,
                            "VatAmount": 0,
                            "Currency": "NOK"
                        },
                        "PricegroupId": -1,
                        "Quantity": 1
                    }
                ]
            }
        },
        {
            "NeedsToSpecifyPricegroups": false,
            "NeedsToSpecifyQuantity": true,
            "Name": "Barnestol",
            "ProducttypeId": 456740,
            "BookedProducts": [],
            "AmountType": "Unlimited",
            "TemplateArguments": {
                "MainProductId": 1,
                "OptionalProducttypeId": 456740,
                "Config": [
                    {
                        "PricegroupName": "Unit",
                        "IsLocalized": false,
                        "Price": {
                            "Price": 175,
                            "VatAmount": 0,
                            "Currency": "NOK"
                        },
                        "PricegroupId": -1,
                        "Quantity": 1
                    }
                ]
            }
        }
    ]
}
```

You will get back a structure that describes the available sub products for the specific product.
Get the basket and use 
`basket.Groups[n].Products[p].BookItemId`
as the mainProductId.

If `NeedsToSpecifyQuantity` is set to `true` you can set it to any value between
0 and 50 depending on the number of units you require.

If `NeedsToSpecifyQuantity` is set to `false` you can set quantity to either 
0 or 1 depending on if you would like to include the product or not.

If `NeedsToSpecifyPricegroups` is set to `true` you need to configure 
each price group item with the specified quantity.

> Let's take a look at the templateArgument section:

```json
            "TemplateArguments": {
                "MainProductId": 1,
                "OptionalProducttypeId": 456740,
                "Config": [
                    {
                        "PricegroupName": "Unit",
                        "IsLocalized": false,
                        "Price": {
                            "Price": 175,
                            "VatAmount": 0,
                            "Currency": "NOK"
                        },
                        "PricegroupId": -1,
                        "Quantity": 1
                    }
                ]
            }
```
It's there to help you decide how to configurate the product. Cross reference this
with the datatype the post takes, you can see that they are identical on some parts.
The price on the outer section is there to tell that the price is valid for 
the entire configuration.
The price in the config section is there to tell the price if it depends on the 
number of units for the specific price group.

Basically, if the sub product is inlcuded as one per guest, that configuration
must be submitted for each guest, also the price is known at that time and presented
on the outer section.

In this case the `NeedsToSpecifyQuantity` is set and you will have to configure how
many items you would like. The price is then presented in the config item so you 
can tell the price depending on the number of units selected.

The `PricegroupId` set to minus one represents that the price is not dependent 
on pricegroup but on the type Unit, meaning that regardless of the age of the 
person associated with the item, the price will be the same.

`IsLocalized` tells the consumer if the price group is generated using the
translation of the price group. If set to `false` you will have to bring your
own translation when presenting in to the user.

> In order to use that configuration you can simply omit some parts:

```json
            {
                "MainProductId": 1,
                "OptionalProducttypeId": 456740,
                "Config": [
                    {
                        "PricegroupId": -1,
                        "Quantity": 1
                    }
                ]
            }
```

There is a valid configuration object that could be used with the SetOptionalProducts method.

The default values (Quantity) will be set to a positive value if the subproduct is 
not configured. When configured, the default value would be to remove it.

### Set optional product
> Set optional products arguments

```shell
See javascript example.
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/guests/add/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
  body: JSON.Stringify([
	{
        "MainProductId": 1,
        "OptionalProducttypeId": 456793,
        "Config": [
            {
                "PricegroupId": -1,
                "Quantity": 3
            }
        ]
    },
    {
        "MainProductId": 1,
        "OptionalProducttypeId": 445409,
        "Config": [
            {
                "PricegroupId": -1,
                "Quantity": 1
            }
        ]
    }
]
);
```

This will configure the first product to be three and the second to be one. 
The other two will be removed if configured. 

Keep in mind that you must at all times configure the sub products that you 
would like. For instance if you add one optional sub product and later you would
like to configure one more, you must submit the configuration for the existing one
in order to keep it. Otherwise it will be removed.

So omitting sub product configurations, means that they should be removed if 
configured.


## Supplier messages

It is possible to send a note to the supplier while acting on the basket.

### Get supplier messages

> Getting supplier messages

```shell
See javascript section.
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/suppliermessage/{basketId}",
{
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json"
    "Accept-Language": "en-US"
  }  
});
```

That will result in a list of available suppliers and the configured messages.

> Response of getting supplier messages

```json
[
    {
        "SupplierName": "HafjellKvitfjell Booking AS - Hytter",
        "SupplierId": 54705,
        "Message": null
    }
]
```

### Set supplier messages

Update the messages by posting to the same url

> Update supplier messages

```shell
See javascript section.
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/suppliermessage/{basketId}",
{
  method:"POST"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
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

The example will set the message to the supplier. You can update one or more messages
to the suppliers with a single post.

## Cancellation insurance

If an cancellation insurance is available, you can find a reference in the basket to it.

> Cancellation insurance in the basket

```json
    /* parts of the basket */
    "CancellationInsurrances": [
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
```

You can configure the cancellation insurance by calling 

https://galaxy.test.citybreak.com/v2/api/basket/cancellation/49989888/97/false
> Update Cancellation Insurance status

```shell
See javascript section.
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/v2/api/basket/cancellation/{basketId}/{insuranceId}/{state}",
{
  method:"PUT"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
    "Accept-Language": "en-US"
  }  
);
```

The state is either `true` or `false`. 

<aside class="notice">
If `CanBeChanged` is false, nothing will happen.
</aside>

The basket price will reflect the new total. 
The insurance is usually based on the types of products that are included in the 
basket right now. It could be fixed per booking, fixed per product or a percentage
of the product cost. Hence the `CurrentCost`.
