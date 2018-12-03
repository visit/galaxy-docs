# Country Code

**Country Code** calls provide information about available country codes for your API key. There are two calls, one to provide all available country codes and one HEAD call to check if a specified country code is supported.

**GET** and **HEAD** operations 

## Country Code

```shell
curl -X GET 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK' 
'https://galaxy.citybreak.com/v3/api/countrycode'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/countrycode",
{
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json"
  }  
});
```

> Example of response:

```json
[
  "SE",
  "US"
]
```

Gets all available country codes for a specified API key.

### HTTP Request

`GET https://galaxy.citybreak.com/v3/api/countrycode`

## Check Country Code

```shell
curl -X HEAD 
--header 'Accept: application/json' 
--header 'apiKey: APIKEY132456789EWOK'
'https://galaxy.citybreak.com/v3/api/countrycode/{CountryCode}'
```

```javascript
var r = fetch("https://galaxy.citybreak.com/v3/api/countrycode/{CountryCode}",
{
  method: "HEAD"
  headers: {
    "ApiKey:" "APIKEY132456789EWOK",
    "Accept": "application/json"
  }  
});
```

> Example of response:

```json
{}
```

Returns a 200 status code if country code is supported, otherwise 404.

### HTTP Request

`HEAD https://galaxy.citybreak.com/v3/api/countrycode/{CountryCode}`