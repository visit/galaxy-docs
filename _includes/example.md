# Example

This is an example section.

## Example

```shell
curl -X GET 
  --header 'ApiKey: APIKEY132456789EWOK'
  --header 'Accept: application/json' 
  --header 'Accept-Language: en-US'
  'https://example.citybreak.com/v1/example'
```

```javascript
var r = fetch("https://example.citybreak.com/v1/example",
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
  "Examples": [
	"Hello World",
	"Ewoks are the best"
  ]
}
```

An example.

### HTTP Request

`POST https://example.citybreak.com/v1/example`

### Query Parameters

Parameter | Type |Description
--------- | ------ | -----------
Accept-Language | Header | The language.

