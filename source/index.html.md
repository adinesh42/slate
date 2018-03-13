---
title: Merak API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - ruby
  - python
  - NodeJs

toc_footers:
  - <a href='https://dashboard.merak.ai' target="_blank">Sign Up for a Developer Key</a>

# includes:
#   - errors

search: true
---

# Introduction

Welcome to the Merak API Documentation! You can use the API endpoints for our different products based on the one chosen in our [dashboard](https://dashboard.merak.ai).

The upload documentation are for individual data upload. For bulk upload API endpoints and methods please contact [Team Merak](mailto:abhinava@merak.ai?Subject=Bulk%20Upload%20API)

# Authentication

> To authorize your request you'll need to generate salt and key from the dashboard
> Make sure to replace `albusdubledore` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [dashboard](https://dashboard.merak.ai).

Albus expects for the API key to be sent with each request

<aside class="notice">
You must replace <code>albusdumbledore</code> with your personal API key.
</aside>

# Albus

## Add User

```ruby
require 'uri'
require 'net/http'
url = URI("https://albus.merak.ai/user")
http = Net::HTTP.new(url.host, url.port)
request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/json'
request["Cache-Control"] = 'no-cache'
request.body = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"user_id\": \"1\", \"gender\": \"male\", \"age_range\": \"18-25\", \"acquisition_channel\": \"google\"},\n\t\"hash\": \"f8acebcf17f0bee73a8d2717a90d6c6e8c3957ded2b60a5632cb5a3d3afefce3eba98c50b7c0e455e931e1c799f87378d487224a15a6c16f0734e22ca776fb02\"\n}"
response = http.request(request)
puts response.read_body
```

```python
import requests
url = "https://albus.merak.ai/user"
payload = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"user_id\": \"1\", \"gender\": \"male\", \"age_range\": \"18-25\", \"acquisition_channel\": \"google\"},\n\t\"hash\": \"f8acebcf17f0bee73a8d2717a90d6c6e8c3957ded2b60a5632cb5a3d3afefce3eba98c50b7c0e455e931e1c799f87378d487224a15a6c16f0734e22ca776fb02\"\n}"
headers = {
  'Content-Type': "application/json",
  'Cache-Control': "no-cache"
}
response = requests.request("POST", url, data=payload, headers=headers)
print(response.text)
```

```NodeJs
var request = require("request")
var options = { 
  method: 'POST',
  url: 'https://albus.merak.ai/user',
  headers: {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json' 
  },
  body: {
    key: 'albusdumbeldore',
    data: { 
      user_id: '1',
      gender: 'male',
      age_range: '18-25',
      acquisition_channel: 'google' 
    },
    hash: 'f8acebcf17f0bee73a8d2717a90d6c6e8c3957ded2b60a5632cb5a3d3afefce3eba98c50b7c0e455e931e1c799f87378d487224a15a6c16f0734e22ca776fb02' 
  },
  json: true 
}
request(options, function (error, response, body) {
  if (error) throw new Error(error)
  console.log(body)
})
```

> The above command returns JSON structured like this:

```json
{
  "data": [],
  "success": 1
}
```

This endpoint inserts a user.

### Hash

`Key|user_id:USER_ID|gender:GENDER|age_range:AGE_RANGE|acquisition_channel:ACQUISITION_CHANNEL|Salt`

### HTTP Request

`POST https://albus.merak.ai/user`

### Query Parameters

Parameter | Description
--------- | -----------
key | The key you obtained from dashboard.
data | user_id is mandatory, rest can be blank.
hash | Please refer to hash section of this API

<!-- <aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->

## Add Product

```ruby
require 'uri'
require 'net/http'
url = URI("https://albus.merak.ai/product")
http = Net::HTTP.new(url.host, url.port)
request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/json'
request["Cache-Control"] = 'no-cache'
request.body = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"product_id\": \"3\", \"category\": \"Apparels\", \"image_link\": \"https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/68dd54ca-60cf-4ef7-898b-26d7cbe48ec7/10-dithering-opt.jpg\", \"color\": \"black\", \"brand\": \"Nike\", \"size\": \"M\", \"price\": \"500\"},\n\t\"hash\": \"49c1be88efb96cc403d8e3abe515c1bf91b0f751bf34d75cb62ba73958fc87a83ba986e0e1e3d973112242395637763ec91feb750bcfd7c4bc8ad6790295b36b\"\n}"
response = http.request(request)
puts response.read_body
```

```python
import requests
url = "https://albus.merak.ai/product"
payload = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"product_id\": \"3\", \"category\": \"Apparels\", \"image_link\": \"https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/68dd54ca-60cf-4ef7-898b-26d7cbe48ec7/10-dithering-opt.jpg\", \"color\": \"black\", \"brand\": \"Nike\", \"size\": \"M\", \"price\": \"500\"},\n\t\"hash\": \"49c1be88efb96cc403d8e3abe515c1bf91b0f751bf34d75cb62ba73958fc87a83ba986e0e1e3d973112242395637763ec91feb750bcfd7c4bc8ad6790295b36b\"\n}"
headers = {
  'Content-Type': "application/json",
  'Cache-Control': "no-cache"
}
response = requests.request("POST", url, data=payload, headers=headers)
print(response.text)
```

```NodeJs
var request = require("request")
var options = { 
  method: 'POST',
  url: 'https://albus.merak.ai/product',
  headers: { 
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json' },
  body: { 
    key: 'albusdumbeldore',
    data: { 
      product_id: '3',
      category: 'Apparels',
      image_link: 'https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/68dd54ca-60cf-4ef7-898b-26d7cbe48ec7/10-dithering-opt.jpg',
      color: 'black',
      brand: 'Nike',
      size: 'M',
      price: '500' 
    },
    hash: '49c1be88efb96cc403d8e3abe515c1bf91b0f751bf34d75cb62ba73958fc87a83ba986e0e1e3d973112242395637763ec91feb750bcfd7c4bc8ad6790295b36b' },
  json: true 
}
request(options, function (error, response, body) {
  if (error) throw new Error(error)
  console.log(body)
})
```

> The above command returns JSON structured like this:

```json
{
  "data": [],
  "success": 1
}
```

This endpoint uploads a product.

<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->
### Hash

`Key|product_id:PRODUCT_ID|category:CATEGORY|image_link:IMAGE_LINK|color:COLOR|brand:BRAND|size:SIZE|price:PRICE|Salt`

### HTTP Request

`POST https://albus.merak.ai/product`

### URL Parameters

Parameter | Description
--------- | -----------
key | The key you obtained from dashboard.
data | product_id is mandatory, rest can be blank.
hash | Please refer to hash section of this API

## Add Activity

```ruby
require 'uri'
require 'net/http'
url = URI("https://albus.merak.ai/activity")
http = Net::HTTP.new(url.host, url.port)
request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/json'
request["Cache-Control"] = 'no-cache'
request.body = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"time\": 1516665030, \"user_id\": \"1\", \"product_id\": \"2\", \"type\": \"view\"},\n\t\"hash\": \"51d5541cbbe17b0030720f3e28753d8d69db444fe1f6c21c189c8dc0d06c933fd8f83a1e5442281ec2d3c564c9df2730c90eaca3e1ca4d1ef5e7adcb3e9bdd7d\"\n}"
response = http.request(request)
puts response.read_body
```

```python
import requests
url = "https://albus.merak.ai/activity"
payload = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"time\": 1516665030, \"user_id\": \"1\", \"product_id\": \"2\", \"type\": \"view\"},\n\t\"hash\": \"51d5541cbbe17b0030720f3e28753d8d69db444fe1f6c21c189c8dc0d06c933fd8f83a1e5442281ec2d3c564c9df2730c90eaca3e1ca4d1ef5e7adcb3e9bdd7d\"\n}"
headers = {
  'Content-Type': "application/json",
  'Cache-Control': "no-cache"
}
response = requests.request("POST", url, data=payload, headers=headers)
print(response.text)
```

```NodeJs
var request = require("request")
var options = { method: 'POST',
  url: 'https://albus.merak.ai/activity',
  headers: {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json' },
  body: { 
    key: 'albusdumbeldore',
    data: { time: 1516665030, user_id: '1', product_id: '2', type: 'view' },
    hash: '51d5541cbbe17b0030720f3e28753d8d69db444fe1f6c21c189c8dc0d06c933fd8f83a1e5442281ec2d3c564c9df2730c90eaca3e1ca4d1ef5e7adcb3e9bdd7d' },
  json: true 
}
request(options, function (error, response, body) {
  if (error) throw new Error(error)
  console.log(body)
})
```

> The above command returns JSON structured like this:

```json
{
  "data": [],
  "success": 1
}
```

This endpoint adds a user activity.

### Activity Types

["view", "likes", "comment", "wishlist", "chat", "cart", "buy"]

### Hash

`Key|time:TIMESTAMP|user_id:USER_ID|product_id:PRODUCT_ID|type:TYPE|Salt`

### HTTP Request

`POST https://albus.merak.ai/activity`

### URL Parameters

Parameter | Description
--------- | -----------
key | The key you obtained from dashboard.
data | All fields are mandatory.
data.time | Unix timestamp
data.type | One among the set of activities types chosen in dashboard
hash | Please refer to hash section of this API

## Prediction

```ruby
require 'uri'
require 'net/http'
url = URI("https://albus.merak.ai/predict")
http = Net::HTTP.new(url.host, url.port)
request = Net::HTTP::Post.new(url)
request["Content-Type"] = 'application/json'
request["Cache-Control"] = 'no-cache'
request.body = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"user_id\": \"1\", \"product_id\": \"2\", \"filter\": {}},\n\t\"hash\": \"fb0f8e1fa175d510e10c314a45247b70cb1fd87c6c878a94bcc6ac8d76d888c2b4be867cf0ef9f9d191707d4bd243499fb85ebe5895d4060b63d6eac0d9b48ae\"\n}"
response = http.request(request)
puts response.read_body
```

```python
import requests
url = "https://albus.merak.ai/predict"
payload = "{\n\t\"key\": \"albusdumbeldore\",\n\t\"data\": {\"user_id\": \"1\", \"product_id\": \"2\", \"filter\": {}},\n\t\"hash\": \"fb0f8e1fa175d510e10c314a45247b70cb1fd87c6c878a94bcc6ac8d76d888c2b4be867cf0ef9f9d191707d4bd243499fb85ebe5895d4060b63d6eac0d9b48ae\"\n}"
headers = {
  'Content-Type': "application/json",
  'Cache-Control': "no-cache"
}
response = requests.request("POST", url, data=payload, headers=headers)
print(response.text)
```

```NodeJs
var request = require("request");
var options = { method: 'POST',
  url: 'https://albus.merak.ai/predict',
  headers: { 
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json' 
  },
  body: { 
    key: 'albusdumbeldore',
    data: { user_id: '1', product_id: '2', filter: {} },
    hash: 'fb0f8e1fa175d510e10c314a45247b70cb1fd87c6c878a94bcc6ac8d76d888c2b4be867cf0ef9f9d191707d4bd243499fb85ebe5895d4060b63d6eac0d9b48ae' 
  },
  json: true 
}
request(options, function (error, response, body) {
  if (error) throw new Error(error)
  console.log(body)
})
```

> The above command returns JSON structured like this:

```json
{
  "success" : 1,
  "data" : [
    {"product_id": "3", "category": "Apparels", "image_link": "https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/68dd54ca-60cf-4ef7-898b-26d7cbe48ec7/10-dithering-opt.jpg", "color": "black", "brand": "Nike", "size": "M", "price": "500"},
    {"product_id": "3", "category": "Apparels", "image_link": "https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/68dd54ca-60cf-4ef7-898b-26d7cbe48ec7/10-dithering-opt.jpg", "color": "black", "brand": "Nike", "size": "M", "price": "500"},
    {"product_id": "3", "category": "Apparels", "image_link": "https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/68dd54ca-60cf-4ef7-898b-26d7cbe48ec7/10-dithering-opt.jpg", "color": "black", "brand": "Nike", "size": "M", "price": "500"}
  ]
}
```

This endpoint fetches the predictions for the user, 10 at a time.

### Filter Structure
`{"filter": {"params": [{"name": "", "value": ""},{"name": "", "value": ""}...], "logic": ["and","or","and","and"...]}}`

### Filter Params
`{"name": "category", "value": []}`
`{"name": "color", "value": []}`
`{"name": "brand", "value": []]}`
`{"name": "size", "value": []}`
`{"name": "price", "value": {"gt": "", "lt": "", "eq": ""}}`

Logic length should be 1 less than Params length

### Hash

`Key|product_id:PRODUCT_ID|user_id:USER_ID|filter:FILTER|Salt`

### HTTP Request

`POST https://albus.merak.ai/predict`

### URL Parameters

Parameter | Description
--------- | -----------
key | The key you obtained from dashboard.
data | user_id and product_id is mandatory, filter can be empty json
data.filter | Please read the filter details
hash | Please refer to hash section of this API

