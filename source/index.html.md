---
Title: InfoBip Web API Interface

Air time Topup: # this a post method
  - airtime topup
  - airtime Topup status

  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://centricgateway.com'>Documentation design by Centric gateway</a>

includes:
  - errors

# Introduction

Welcome to the InfoBip API Interface! .

# /airtime/topup

> To topup airtime, use this given sample code:

>Authorization parameter provided in header to authenticate the API call

```String
Default value : Bearer Test
```
# Body
>Transaction parameters that are needed to perform topup request

```json
{
  "publickey": "test",
  "source": {
    "operation": "airtime_topup",
    "account": {
      "recipient": "2348193645321"
    }
  },
  "transaction": {
    "reference": "TRX_1234"
  },
  "order": {
    "country": "NG",
    "currency": "NGN",
    "amount": 100
  }
}
```

`parameter content-type : application/json`

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Response content-type : application/json`


# /airtime/topup/status

>Airtime topup status, use this given sample code:

>Authorization parameter provided in header to authenticate the API call

```String
Default value : Bearer Test
```
# Body
>Transaction parameters that are needed to perform airtime topup status

>Transaction parameters that are needed to perform status request
```json
{
  "publickey": "test",
  "transaction": {
    "reference": "TRX_1234"
  },
  "source": {
    "operation": "airtime_topup_status"
  }
}
```

`parameter content-type : application/json`

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Response content-type : application/json`

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
