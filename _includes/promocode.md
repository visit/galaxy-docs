# Promo code

**Promo code** call validates entered promotion code for specified `PointOfSalesId`. Result can be filtered based on specific `ProductId`

## Promo code

```shell
curl -X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
-d '{
   "PointOfSalesId": 13633,
   "PromoCodeInfo": [
     {
       "PromoCode": "KOMTILBAKE2020"
     }
   ]
 }' 'https://galaxy.citybreak.com/v5/api/promocode/validate'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v5/api/promocode/validate",
{
	method: "POST",
	headers: {
	    "ApiKey": "APIKEY132456789EWOK",
	    "Accept": "application/json",
	},
	body: JSON.Stringify({
	   "PointOfSalesId": 13633,
	   "PromoCodeInfo": [
	     {
	       "PromoCode": "KOMTILBAKE2020"
	     }
	   ]
	})  
});
```

> Example of response:

```json
{
  "PointOfSalesId": 13633,
  "ValidationResult": [
    {
      "PromoCode": "KOMTILBAKE2020",
      "PromoCodeStatus": "Valid",
      "ProductId": null,
      "Operations": [
        {
          "System": "Xenon-63207",
          "Account": "Xenon-63207",
          "Action": "Search",
          "Duration": "00:00:00.1210295",
          "Success": true,
          "ErrorMessage": null
        }
      ]
    }
  ]
}
```

This is a **POST** request that validates the promotion code for specific PointOfSales. 

### HTTP Request

`POST https://galaxy.citybreak.com/v5/api/promocode/validate`

### Query Parameters

Parameter | Description
--------- | -----------
request | the POST request

<code class="center-column">
{
  "PointOfSalesId": 0, //int - Mandatory
  //List of promotion codes for validation
  //Cannot be empty, must represent at least one promotion code
  "PromoCodeInfo": [
      {
          "PromoCode": "string", //Mandatory - promotion code
          "ProductId": "string" //Optional - product filtering 
      }
  ]
}
</code>
