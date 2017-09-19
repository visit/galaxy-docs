# Basket

> Basket

**Basket** calls are the most complicated in the API workflow as they encapsulate the booking process in typical "shopping basket" object that can have many operations performed on it and which has a limited life span, connected as it is to availability/bookability of products, both internal to Citybreak and from external inventories.

<aside class="notice">NB: if using the Visit Test Organisation API Key you can use 17692 as the **{pointOfSalesId}**</aside>
## Create

```shell
curl -X POST 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/api/basket/create/{pointofSalesId}/{currency}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/api/basket/create/{PointofSalesId}/{Currency}",
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
