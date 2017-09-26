# Basket

> Basket

**Basket** calls are the most complicated in the API workflow as they encapsulate the booking process in typical "shopping basket" object that can have many operations performed on it and which has a limited life span, connected as it is to availability/bookability of products, both internal to Citybreak and from external inventories. It is NOT a reservation but products in a basket will be "held" for 15 mins where this is possible (i.e. where external inventories allow).

<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the **{pointOfSalesId}**</aside>




## Create

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.test.citybreak.com/api/basket/create/{pointofSalesId}/{currency}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/basket/create/{PointofSalesId}/{Currency}",
{
  method:"POST"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
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

`GET https://galaxy.citybreak.com/api/content/attribute`

### Query Parameters

Parameter | Description
--------- | -----------
pointOfSalesId | The point of sales identifier.
currency | The currency of the basket




## Delete

```shell
curl -X DELETE 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.test.citybreak.com/api/basket/delete/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/basket/delete/{basketId}",
{
  method:"DELETE"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
  }  
});
```

> Example of response:

```json
true
```

Delete a basket. This will remove all associated information attached to the basket as well.

### HTTP Request

`DELETE https://galaxy.citybreak.com/api/basket/delete`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket to delete.







## Get

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.test.citybreak.com/api/basket/{basketId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/basket/{basketId}",
{
  method:"GET"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
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
          "MandatoryAddons": [
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
              "GuestLinkId": 10,
              "PriceGroupName": "Vuxen",
              "Guest": {
                "GuestId": 6,
                "NameFirst": null,
                "NameLast": null,
                "Age": -1,
                "Sex": null,
                "Salutation": null
              }
            },
            {
              "GuestLinkId": 11,
              "PriceGroupName": "Barn 0-11",
              "Guest": {
                "GuestId": 7,
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

`Get https://galaxy.citybreak.com/api/basket`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket to get.








## Add Booking Item

```shell
curl -X PUT 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.test.citybreak.com/api/basket/add/accommodation/{basketId}/{searchId}/{bookingKey}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/api/basket/add/accommodation/{basketId}/{searchId}/{bookingKey}",
{
  method:"PUT"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
  }  
});
```

> Example of response:

```json
true
```

Delete a booking item from the basket. In the <a href="https://visit.github.io/galaxy-docs/#basket">Get Basket</a>

### HTTP Request

`PUT https://galaxy.citybreak.com/api/basket/deleteItem`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
searchId | The search Id returned by the <a href="https://visit.github.io/galaxy-docs/#Availability">Availability Response</a>
bookingKey | The key of the booking item to add to the basket, found in <a href="https://visit.github.io/galaxy-docs/#Availability">Availability Response</a>







## Delete Booking Item

```shell
curl -X DELETE 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.test.citybreak.com/api/basket/deleteItem/{basketId}/{bookItemId}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/basket/deleteItem/{basketId}/{bookItemId}",
{
  method:"DELETE"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
  }  
});
```

> Example of response:

```json
true
```

Delete a booking item from the basket. In the <a href="https://visit.github.io/galaxy-docs/#basket">Get Basket</a>

### HTTP Request

`DELETE https://galaxy.citybreak.com/api/basket/deleteItem`

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
'https://galaxy.test.citybreak.com/api/basket/cancellation/{basketId}/{cancellationId}/{true|false}'
```

```javascript
var r = fetch("https://galaxy.test.citybreak.com/api/basket/cancellation/{basketId}/{cancellationId}/{true|false}",
{
  method:"PUT"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json",
  }  
});
```

> Example of response:

```json
Status code 204
```

If your basket has a set of cancellation insurances you can use this call to add one (true) or switch it off (false)

### HTTP Request

`PUT https://galaxy.citybreak.com/api//basket/cancellation`

### Query Parameters

Parameter | Description
--------- | -----------
basketId | The Id of the basket.
cancellationId | The Id of the cancellation insurance to toggle
state | true (added) or false (not added)


