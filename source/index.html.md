---
title: Primaccess API v1.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2


---


<h1 id="Primaccess-API">Primaccess API v1.0</h1>


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


# Request format
Our API only support JSON-encoded data as requests and responses.
Headers for both the `Content-Type` and `Accept` should be set to `application/json`.


# Errors
Occasionally you might encounter errors when accessing the REST API.
Error code | Error message
---------- | -------------
`400 Bad Request` | Everything worked as expected.
`401 Unauthorized` | No valid API key provided.
`404 Not Found` | The requested resource doesn't exist.
`500 Internal Server Error` | Something went wrong.
Errors return both an appropriate HTTP status code and response object which contains a `code`, `message`.


# Dates and times
All dates and times in the API are in **UTC**. This means that when submitting dates and times in your requests your payload should include date/time in **UTC**.
When processing dates and times in responses from the API you should translate them to the local time of the associated outlet.


Base URLs:


* <a href="https://primaccess-179015.appspot.com/">https://primaccess-179015.appspot.com/</a>


# Authentication


* API Key (ApiKeyAuth)
    - Parameter Name: **X-API-Key**, in: header. 


<h1 id="Primaccess-API-Accounts">Accounts</h1>


## searchAccounts


<a id="opIdsearchAccounts"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//accounts \
  -H 'Accept: application/json'


```


```http
GET https://primaccess-179015.appspot.com//accounts HTTP/1.1
Host: primaccess-179015.appspot.com


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//accounts',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'https://primaccess-179015.appspot.com//accounts',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('https://primaccess-179015.appspot.com//accounts', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /accounts`


*Get all accounts*


Returns a list of accounts you’ve previously created.


<h3 id="searchAccounts-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|reference|query|string|false|The own account reference in your application|
|last_name|query|string|false|The account's last name|
|first_name|query|string|false|The account's first name|
|email|query|string|false|The account's email address|
|phone|query|string|false|The account's phone number|
|sort|query|string|false|List of fields for sorting, seperated by comma|
|range|query|string|false|The range of items to return (start-end)|


> Example responses


```json
{
  "total": 100,
  "offset": 0,
  "limit": 20
}
```


<h3 id="searchAccounts-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of account objects|Inline|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## createAccount


<a id="opIdcreateAccount"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com//accounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST https://primaccess-179015.appspot.com//accounts HTTP/1.1
Host: primaccess-179015.appspot.com
Content-Type: application/json
Accept: application/json


```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304",
  "is_superuser": false
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//accounts',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}


result = RestClient.post 'https://primaccess-179015.appspot.com//accounts',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}


r = requests.post('https://primaccess-179015.appspot.com//accounts', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /accounts`


*Create account*


Creates a new account.


> Body parameter


```json
{
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304",
  "is_superuser": false
}
```


<h3 id="createAccount-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Account](#schemaaccount)|true|A partial account object|


> Example responses


```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304",
  "is_superuser": false,
  "created_at": "2017-02-12T15:19:21+01:00",
  "updated_at": "2017-02-12T15:19:21-02:00"
}
```


<h3 id="createAccount-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|An account object|Inline|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getAccount


<a id="opIdgetAccount"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//accounts/{account_id} \
  -H 'Accept: application/json'


```


```http
GET https://primaccess-179015.appspot.com//accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts/{account_id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//accounts/{account_id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'https://primaccess-179015.appspot.com//accounts/{account_id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('https://primaccess-179015.appspot.com//accounts/{account_id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /accounts/{account_id}`


*Get account*


Get info about an account.


<h3 id="getAccount-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Unique identifier for the account|


> Example responses


```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304",
  "is_superuser": false,
  "created_at": "2017-02-12T15:19:21+01:00",
  "updated_at": "2017-02-12T15:19:21-02:00"
}
```
```json
{
  "code": "string",
  "message": "string"
}
```


<h3 id="getAccount-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|An account object|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found.|[Error](#schemaerror)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## updateAccount


<a id="opIdupdateAccount"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//accounts/{account_id}


```


```http
PUT https://primaccess-179015.appspot.com//accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts/{account_id}',
  method: 'put',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//accounts/{account_id}',
{
  method: 'PUT'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.put 'https://primaccess-179015.appspot.com//accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.put('https://primaccess-179015.appspot.com//accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /accounts/{account_id}`


*Update account*


Updates an existing account.


<h3 id="updateAccount-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="updateAccount-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|An account object|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## removeAccount


<a id="opIdremoveAccount"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com//accounts/{account_id}


```


```http
DELETE https://primaccess-179015.appspot.com//accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts/{account_id}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//accounts/{account_id}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'https://primaccess-179015.appspot.com//accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.delete('https://primaccess-179015.appspot.com//accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /accounts/{account_id}`


*Remove account*


Removes an existing account.


<h3 id="removeAccount-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="removeAccount-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content - Account deleted successfully|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getAccountCards


<a id="opIdgetAccountCards"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//accounts/{account_id}/cards


```


```http
GET https://primaccess-179015.appspot.com//accounts/{account_id}/cards HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts/{account_id}/cards',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//accounts/{account_id}/cards',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//accounts/{account_id}/cards',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//accounts/{account_id}/cards', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts/{account_id}/cards");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /accounts/{account_id}/cards`


*Get all cards*


Gets all cards of an account.


<h3 id="getAccountCards-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="getAccountCards-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of card objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getAccountWallets


<a id="opIdgetAccountWallets"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//accounts/{account_id}/wallets


```


```http
GET https://primaccess-179015.appspot.com//accounts/{account_id}/wallets HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts/{account_id}/wallets',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//accounts/{account_id}/wallets',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//accounts/{account_id}/wallets',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//accounts/{account_id}/wallets', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts/{account_id}/wallets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /accounts/{account_id}/wallets`


*Get all wallets*


Gets all wallets of an account.


<h3 id="getAccountWallets-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="getAccountWallets-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of wallet objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getAccountTransactions


<a id="opIdgetAccountTransactions"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//accounts/{account_id}/transactions


```


```http
GET https://primaccess-179015.appspot.com//accounts/{account_id}/transactions HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts/{account_id}/transactions',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//accounts/{account_id}/transactions',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//accounts/{account_id}/transactions',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//accounts/{account_id}/transactions', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts/{account_id}/transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /accounts/{account_id}/transactions`


*Get all transactions*


Gets all transactions of an account.


<h3 id="getAccountTransactions-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="getAccountTransactions-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of transaction objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getAccountMoves


<a id="opIdgetAccountMoves"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//accounts/{account_id}/moves


```


```http
GET https://primaccess-179015.appspot.com//accounts/{account_id}/moves HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//accounts/{account_id}/moves',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//accounts/{account_id}/moves',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//accounts/{account_id}/moves',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//accounts/{account_id}/moves', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//accounts/{account_id}/moves");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /accounts/{account_id}/moves`


*Get all moves*


Gets all moves of an account.


<h3 id="getAccountMoves-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="getAccountMoves-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of move objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


<h1 id="Primaccess-API-Wallets">Wallets</h1>


## createWallet


<a id="opIdcreateWallet"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com//wallets \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST https://primaccess-179015.appspot.com//wallets HTTP/1.1
Host: primaccess-179015.appspot.com
Content-Type: application/json
Accept: application/json


```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "Golf store",
  "practice_availability": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//wallets',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}


result = RestClient.post 'https://primaccess-179015.appspot.com//wallets',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}


r = requests.post('https://primaccess-179015.appspot.com//wallets', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /wallets`


*Create wallet*


Creates a new wallet.


> Body parameter


```json
{
  "name": "Golf store",
  "practice_availability": true
}
```


<h3 id="createWallet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Wallet](#schemawallet)|true|A partial wallet object|


> Example responses


```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Golf store",
  "practice_availability": true,
  "balance": 10.5,
  "created_at": "2017-02-12T15:19:21+01:00",
  "updated_at": "2017-02-12T15:19:21-02:00"
}
```


<h3 id="createWallet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|A wallet objet|Inline|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getWallet


<a id="opIdgetWallet"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//wallets/{wallet_id} \
  -H 'Accept: application/json'


```


```http
GET https://primaccess-179015.appspot.com//wallets/{wallet_id} HTTP/1.1
Host: primaccess-179015.appspot.com


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets/{wallet_id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//wallets/{wallet_id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'https://primaccess-179015.appspot.com//wallets/{wallet_id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('https://primaccess-179015.appspot.com//wallets/{wallet_id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets/{wallet_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /wallets/{wallet_id}`


*Get wallet*


Gets info about a wallet.


<h3 id="getWallet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|wallet_id|path|string|true|Unique identifier for the wallet|


> Example responses


```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Golf store",
  "practice_availability": true,
  "balance": 10.5,
  "created_at": "2017-02-12T15:19:21+01:00",
  "updated_at": "2017-02-12T15:19:21-02:00"
}
```


<h3 id="getWallet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A wallet object|Inline|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## updateWallet


<a id="opIdupdateWallet"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//wallets/{wallet_id}


```


```http
PUT https://primaccess-179015.appspot.com//wallets/{wallet_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets/{wallet_id}',
  method: 'put',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//wallets/{wallet_id}',
{
  method: 'PUT'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.put 'https://primaccess-179015.appspot.com//wallets/{wallet_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.put('https://primaccess-179015.appspot.com//wallets/{wallet_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets/{wallet_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /wallets/{wallet_id}`


*Update wallet*


Updates an existing wallet.


<h3 id="updateWallet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|wallet_id|path|string|true|Unique identifier for the wallet|


<h3 id="updateWallet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A wallet object|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## removeWallet


<a id="opIdremoveWallet"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com//wallets/{wallet_id}


```


```http
DELETE https://primaccess-179015.appspot.com//wallets/{wallet_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets/{wallet_id}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//wallets/{wallet_id}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'https://primaccess-179015.appspot.com//wallets/{wallet_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.delete('https://primaccess-179015.appspot.com//wallets/{wallet_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets/{wallet_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /wallets/{wallet_id}`


*Remove wallet*


Removes an existing wallet.


<h3 id="removeWallet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|wallet_id|path|string|true|Unique identifier for the wallet|


<h3 id="removeWallet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content - Wallet deleted successfully|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getWalletAccounts


<a id="opIdgetWalletAccounts"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts


```


```http
GET https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /wallets/{wallet_id}/accounts`


*Get all accounts*


Get all accounts on a wallet.


<h3 id="getWalletAccounts-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|wallet_id|path|string|true|Unique identifier for the wallet|


<h3 id="getWalletAccounts-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of account objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getTransactionsByWalletId


<a id="opIdgetTransactionsByWalletId"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//wallets/{wallet_id}/transactions


```


```http
GET https://primaccess-179015.appspot.com//wallets/{wallet_id}/transactions HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/transactions',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//wallets/{wallet_id}/transactions',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/transactions',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//wallets/{wallet_id}/transactions', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets/{wallet_id}/transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /wallets/{wallet_id}/transactions`


*Get all transactions*


Gets all transactions of a wallet.


<h3 id="getTransactionsByWalletId-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|wallet_id|path|string|true|Unique identifier for the wallet|


<h3 id="getTransactionsByWalletId-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of transaction objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## addAccountToWallet


<a id="opIdaddAccountToWallet"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}


```


```http
PUT https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}',
  method: 'put',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}',
{
  method: 'PUT'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.put 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.put('https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /wallets/{wallet_id}/accounts/{account_id}`


*Add account*


Adds an account to a wallet.


<h3 id="addAccountToWallet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|wallet_id|path|string|true|Unique identifier for the wallet|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="addAccountToWallet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## removeAccountFromWallet


<a id="opIdremoveAccountFromWallet"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}


```


```http
DELETE https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.delete('https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//wallets/{wallet_id}/accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /wallets/{wallet_id}/accounts/{account_id}`


*Remove account*


Removes an account from a wallet.


<h3 id="removeAccountFromWallet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|wallet_id|path|string|true|Unique identifier for the wallet|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="removeAccountFromWallet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


<h1 id="Primaccess-API-Cards">Cards</h1>


## getCard


<a id="opIdgetCard"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//cards/{card_id} \
  -H 'Accept: application/json'


```


```http
GET https://primaccess-179015.appspot.com//cards/{card_id} HTTP/1.1
Host: primaccess-179015.appspot.com


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//cards/{card_id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//cards/{card_id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get 'https://primaccess-179015.appspot.com//cards/{card_id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('https://primaccess-179015.appspot.com//cards/{card_id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//cards/{card_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /cards/{card_id}`


*Get card*


Gets info about a card.


<h3 id="getCard-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|card_id|path|string|true|Unique identifier for the card|


> Example responses


```json
{
  "id": "040F1848D7581"
}
```


<h3 id="getCard-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A card object|[Card](#schemacard)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getCardOwners


<a id="opIdgetCardOwners"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//cards/{card_id}/accounts


```


```http
GET https://primaccess-179015.appspot.com//cards/{card_id}/accounts HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//cards/{card_id}/accounts',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//cards/{card_id}/accounts',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//cards/{card_id}/accounts',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//cards/{card_id}/accounts', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//cards/{card_id}/accounts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /cards/{card_id}/accounts`


*Get all owners*


Gets all owners for a card.


<h3 id="getCardOwners-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|card_id|path|string|true|Unique identifier for the card|


<h3 id="getCardOwners-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of card owner objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## assignCard


<a id="opIdassignCard"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}


```


```http
PUT https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}',
  method: 'put',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}',
{
  method: 'PUT'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.put 'https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.put('https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /cards/{card_id}/accounts/{account_id}`


*Assign card*


Assigns card to an account.


<h3 id="assignCard-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|card_id|path|string|true|Unique identifier for the card|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="assignCard-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## unassignCard


<a id="opIdunassignCard"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}


```


```http
DELETE https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.delete('https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//cards/{card_id}/accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /cards/{card_id}/accounts/{account_id}`


*Unassign card*


Unassigns card from an account.


<h3 id="unassignCard-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|card_id|path|string|true|Unique identifier for the card|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="unassignCard-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


<h1 id="Primaccess-API-Groups">Groups</h1>


## getGroups


<a id="opIdgetGroups"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//groups/


```


```http
GET https://primaccess-179015.appspot.com//groups/ HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//groups/',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//groups/',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//groups/',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//groups/', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//groups/");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /groups/`


*Get all groups*


Gets all groups for the current golf.


<h3 id="getGroups-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of group objects|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## createGroup


<a id="opIdcreateGroup"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com//groups/ \
  -H 'Accept: application/json'


```


```http
POST https://primaccess-179015.appspot.com//groups/ HTTP/1.1
Host: primaccess-179015.appspot.com


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//groups/',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//groups/',
{
  method: 'POST',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.post 'https://primaccess-179015.appspot.com//groups/',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.post('https://primaccess-179015.appspot.com//groups/', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//groups/");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /groups/`


*Create group*


Creates a new group.


> Example responses


```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Professionals",
  "access": [
    {
      "endpoint": {
        "name": "Practice",
        "fee": 2.5,
        "version": "1.0.1",
        "last_boot_at": "2017-02-12T15:19:21-02:00",
        "last_ntf_at": "2017-02-12T15:19:21-02:00"
      },
      "daily_access": {
        "monday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "tuesday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "wednesday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "thursday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "friday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "saturday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "sunday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ]
      }
    }
  ],
  "created_at": "2017-02-12T15:19:21+01:00",
  "updated_at": "2017-02-12T15:19:21-02:00"
}
```


<h3 id="createGroup-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|A group object|Inline|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## updateGroup


<a id="opIdupdateGroup"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//groups/{group_id} \
  -H 'Accept: application/json'


```


```http
PUT https://primaccess-179015.appspot.com//groups/{group_id} HTTP/1.1
Host: primaccess-179015.appspot.com


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: 'https://primaccess-179015.appspot.com//groups/{group_id}',
  method: 'put',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('https://primaccess-179015.appspot.com//groups/{group_id}',
{
  method: 'PUT',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.put 'https://primaccess-179015.appspot.com//groups/{group_id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.put('https://primaccess-179015.appspot.com//groups/{group_id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//groups/{group_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /groups/{group_id}`


*Update group*


Updates an existing group.


<h3 id="updateGroup-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|group_id|path|string|true|Unique identifier for the group|


> Example responses


```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Professionals",
  "access": [
    {
      "endpoint": {
        "name": "Practice",
        "fee": 2.5,
        "version": "1.0.1",
        "last_boot_at": "2017-02-12T15:19:21-02:00",
        "last_ntf_at": "2017-02-12T15:19:21-02:00"
      },
      "daily_access": {
        "monday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "tuesday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "wednesday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "thursday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "friday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "saturday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "sunday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ]
      }
    }
  ],
  "created_at": "2017-02-12T15:19:21+01:00",
  "updated_at": "2017-02-12T15:19:21-02:00"
}
```


<h3 id="updateGroup-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A group object|Inline|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## removeGroup


<a id="opIdremoveGroup"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com//groups/{group_id}


```


```http
DELETE https://primaccess-179015.appspot.com//groups/{group_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//groups/{group_id}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//groups/{group_id}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'https://primaccess-179015.appspot.com//groups/{group_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.delete('https://primaccess-179015.appspot.com//groups/{group_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//groups/{group_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /groups/{group_id}`


*Remove group*


Removes an existing group.


<h3 id="removeGroup-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|group_id|path|string|true|Unique identifier for the group|


<h3 id="removeGroup-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## addAccountToGroup


<a id="opIdaddAccountToGroup"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}


```


```http
PUT https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}',
  method: 'put',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}',
{
  method: 'PUT'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.put 'https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.put('https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /groups/{group_id}/accounts/{account_id}`


*Add account*


Adds an account to a group.


<h3 id="addAccountToGroup-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|group_id|path|string|true|Unique identifier for the group|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="addAccountToGroup-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## removeAccountFromGroup


<a id="opIdremoveAccountFromGroup"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}


```


```http
DELETE https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.delete('https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//groups/{group_id}/accounts/{account_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /groups/{group_id}/accounts/{account_id}`


*Remove account*


Removes an account from a group.


<h3 id="removeAccountFromGroup-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|group_id|path|string|true|Unique identifier for the group|
|account_id|path|string|true|Unique identifier for the account|


<h3 id="removeAccountFromGroup-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


<h1 id="Primaccess-API-Transactions">Transactions</h1>


## getTransactionTypes


<a id="opIdgetTransactionTypes"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//transactions/types


```


```http
GET https://primaccess-179015.appspot.com//transactions/types HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions/types',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions/types',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//transactions/types',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//transactions/types', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions/types");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /transactions/types`


*Get a list of transaction types from the current golf*


<h3 id="getTransactionTypes-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## createTransactionType


<a id="opIdcreateTransactionType"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com//transactions/types


```


```http
POST https://primaccess-179015.appspot.com//transactions/types HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions/types',
  method: 'post',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions/types',
{
  method: 'POST'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.post 'https://primaccess-179015.appspot.com//transactions/types',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.post('https://primaccess-179015.appspot.com//transactions/types', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions/types");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /transactions/types`


*Create a transaction type*


<h3 id="createTransactionType-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getTransactionTypeById


<a id="opIdgetTransactionTypeById"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}


```


```http
GET https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /transactions/types/{transaction_type_id}`


*Get information about a transaction type*


<h3 id="getTransactionTypeById-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|transaction_type_id|path|string|true|No description|


<h3 id="getTransactionTypeById-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## updateTransactionType


<a id="opIdupdateTransactionType"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}


```


```http
PUT https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
  method: 'put',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
{
  method: 'PUT'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.put 'https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.put('https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /transactions/types/{transaction_type_id}`


*Update a transaction type*


<h3 id="updateTransactionType-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## deleteTransactionType


<a id="opIddeleteTransactionType"></a>


> Code samples


```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}


```


```http
DELETE https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.delete 'https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.delete('https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions/types/{transaction_type_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`DELETE /transactions/types/{transaction_type_id}`


*Delete a transaction type*


<h3 id="deleteTransactionType-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## searchTransactions


<a id="opIdsearchTransactions"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//transactions


```


```http
GET https://primaccess-179015.appspot.com//transactions HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//transactions',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//transactions', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /transactions`


*Search for transactions*


<h3 id="searchTransactions-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## createTransaction


<a id="opIdcreateTransaction"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com//transactions


```


```http
POST https://primaccess-179015.appspot.com//transactions HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions',
  method: 'post',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions',
{
  method: 'POST'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.post 'https://primaccess-179015.appspot.com//transactions',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.post('https://primaccess-179015.appspot.com//transactions', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /transactions`


*Create a transaction*


<h3 id="createTransaction-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getTransactionById


<a id="opIdgetTransactionById"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//transactions/{id}


```


```http
GET https://primaccess-179015.appspot.com//transactions/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//transactions/{id}',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//transactions/{id}',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//transactions/{id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//transactions/{id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//transactions/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /transactions/{id}`


*Get information about a transaction*


<h3 id="getTransactionById-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|No description|


<h3 id="getTransactionById-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


<h1 id="Primaccess-API-Endpoints">Endpoints</h1>


## getEndpoints


<a id="opIdgetEndpoints"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//endpoints


```


```http
GET https://primaccess-179015.appspot.com//endpoints HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//endpoints',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//endpoints',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//endpoints',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//endpoints', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//endpoints");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /endpoints`


*Get a list of endpoints by the current golf*


<h3 id="getEndpoints-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getEndpointById


<a id="opIdgetEndpointById"></a>


> Code samples


```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com//endpoints/{id}


```


```http
PUT https://primaccess-179015.appspot.com//endpoints/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//endpoints/{id}',
  method: 'put',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//endpoints/{id}',
{
  method: 'PUT'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.put 'https://primaccess-179015.appspot.com//endpoints/{id}',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.put('https://primaccess-179015.appspot.com//endpoints/{id}', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//endpoints/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`PUT /endpoints/{id}`


*Modify the endpoint*


<h3 id="getEndpointById-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|No description|


<h3 id="getEndpointById-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


<h1 id="Primaccess-API-Access">Access</h1>


## searchAccess


<a id="opIdsearchAccess"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//access


```


```http
GET https://primaccess-179015.appspot.com//access HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//access',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//access',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//access',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//access', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//access");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /access`


*Search for access rights*


<h3 id="searchAccess-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## createAccess


<a id="opIdcreateAccess"></a>


> Code samples


```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com//access


```


```http
POST https://primaccess-179015.appspot.com//access HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//access',
  method: 'post',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//access',
{
  method: 'POST'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.post 'https://primaccess-179015.appspot.com//access',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.post('https://primaccess-179015.appspot.com//access', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//access");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /access`


*Create access rights*


Date et heure au format [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601#Times) (système horaire sur 24 heures).
L'heure donnée sera arrondie à la demie-heure inférieure. Seules les valeurs *00* ou *30* sont prises en compte par le système.
Une journée commence à **00:00** et termine à **24:00**.


<h3 id="createAccess-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


<h1 id="Primaccess-API-Miscellaneous">Miscellaneous</h1>


## searchMoves


<a id="opIdsearchMoves"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//moves


```


```http
GET https://primaccess-179015.appspot.com//moves HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//moves',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//moves',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//moves',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//moves', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//moves");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /moves`


*Search for moves*


<h3 id="searchMoves-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


## getAttendance


<a id="opIdgetAttendance"></a>


> Code samples


```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com//attendance


```


```http
GET https://primaccess-179015.appspot.com//attendance HTTP/1.1
Host: primaccess-179015.appspot.com


```


```javascript


$.ajax({
  url: 'https://primaccess-179015.appspot.com//attendance',
  method: 'get',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


fetch('https://primaccess-179015.appspot.com//attendance',
{
  method: 'GET'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://primaccess-179015.appspot.com//attendance',
  params: {
  }


p JSON.parse(result)


```


```python
import requests


r = requests.get('https://primaccess-179015.appspot.com//attendance', params={


)


print r.json()


```


```java
URL obj = new URL("https://primaccess-179015.appspot.com//attendance");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /attendance`


*Get statistics about attendance*


<h3 id="getAttendance-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>


# Schemas


<h2 id="tocSaccount">Account</h2>


<a id="schemaaccount"></a>


```json
{
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304",
  "is_superuser": false
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|reference|string|false|No description|
|last_name|string|false|No description|
|first_name|string|false|No description|
|email|string|false|No description|
|phone|string|false|No description|
|is_superuser|boolean|false|No description|


<h2 id="tocSwallet">Wallet</h2>


<a id="schemawallet"></a>


```json
{
  "name": "Golf store",
  "practice_availability": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|name|string|false|No description|
|practice_availability|boolean|false|No description|


<h2 id="tocScard">Card</h2>


<a id="schemacard"></a>


```json
{
  "id": "040F1848D7581"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|


<h2 id="tocSgroup">Group</h2>


<a id="schemagroup"></a>


```json
{
  "name": "Professionals",
  "access": [
    {
      "endpoint": {
        "name": "Practice",
        "fee": 2.5,
        "version": "1.0.1",
        "last_boot_at": "2017-02-12T15:19:21-02:00",
        "last_ntf_at": "2017-02-12T15:19:21-02:00"
      },
      "daily_access": {
        "monday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "tuesday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "wednesday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "thursday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "friday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "saturday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ],
        "sunday": [
          {
            "from": "11:30",
            "to": "14:00"
          }
        ]
      }
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|name|string|false|No description|
|access|[allOf]|false|No description|


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|» *anonymous*|object|false|No description|
|»» endpoint|[Endpoint](#schemaendpoint)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|» *anonymous*|[WeekAccess](#schemaweekaccess)|false|No description|


<h2 id="tocSendpoint">Endpoint</h2>


<a id="schemaendpoint"></a>


```json
{
  "name": "Practice",
  "fee": 2.5,
  "version": "1.0.1",
  "last_boot_at": "2017-02-12T15:19:21-02:00",
  "last_ntf_at": "2017-02-12T15:19:21-02:00"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|name|string|false|No description|
|fee|number|false|No description|
|version|string|false|No description|
|last_boot_at|string(datetime)|false|No description|
|last_ntf_at|string(datetime)|false|No description|


<h2 id="tocStransaction">Transaction</h2>


<a id="schematransaction"></a>


```json
{
  "wallet_id": "string",
  "reference": "string",
  "name": "string",
  "amount": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|wallet_id|string|false|No description|
|reference|string|false|No description|
|name|string|false|No description|
|amount|number|false|No description|


<h2 id="tocSmove">Move</h2>


<a id="schemamove"></a>


```json
{
  "endpoint_id": "string",
  "card_owner_id": "string",
  "fee": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|endpoint_id|string|false|Endpoint uuid|
|card_owner_id|string|false|CardOwner uuid|
|fee|number|false|Move swipe fee|


<h2 id="tocScardowner">CardOwner</h2>


<a id="schemacardowner"></a>


```json
{
  "account": {
    "reference": "AAAA-BBBB",
    "last_name": "Doe",
    "first_name": "John",
    "email": "john.doe@gmail.com",
    "phone": "0601020304",
    "is_superuser": false
  },
  "assign_on": "2017-02-12T15:19:21+01:00"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|account|[Account](#schemaaccount)|false|No description|
|assign_on|string|false|No description|


<h2 id="tocSweekaccess">WeekAccess</h2>


<a id="schemaweekaccess"></a>


```json
{
  "daily_access": {
    "monday": [
      {
        "from": "11:30",
        "to": "14:00"
      }
    ],
    "tuesday": [
      {
        "from": "11:30",
        "to": "14:00"
      }
    ],
    "wednesday": [
      {
        "from": "11:30",
        "to": "14:00"
      }
    ],
    "thursday": [
      {
        "from": "11:30",
        "to": "14:00"
      }
    ],
    "friday": [
      {
        "from": "11:30",
        "to": "14:00"
      }
    ],
    "saturday": [
      {
        "from": "11:30",
        "to": "14:00"
      }
    ],
    "sunday": [
      {
        "from": "11:30",
        "to": "14:00"
      }
    ]
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|daily_access|object|false|No description|
|» monday|[[TimeSlot](#schematimeslot)]|false|No description|
|» tuesday|[[TimeSlot](#schematimeslot)]|false|No description|
|» wednesday|[[TimeSlot](#schematimeslot)]|false|No description|
|» thursday|[[TimeSlot](#schematimeslot)]|false|No description|
|» friday|[[TimeSlot](#schematimeslot)]|false|No description|
|» saturday|[[TimeSlot](#schematimeslot)]|false|No description|
|» sunday|[[TimeSlot](#schematimeslot)]|false|No description|


<h2 id="tocStimeslot">TimeSlot</h2>


<a id="schematimeslot"></a>


```json
{
  "from": "11:30",
  "to": "14:00"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|from|number|false|No description|
|to|number|false|No description|


<h2 id="tocSid">Id</h2>


<a id="schemaid"></a>


```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|true|No description|


<h2 id="tocScreatedat">CreatedAt</h2>


<a id="schemacreatedat"></a>


```json
{
  "created_at": "2017-02-12T15:19:21+01:00"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|created_at|string|false|No description|


<h2 id="tocSupdatedat">UpdatedAt</h2>


<a id="schemaupdatedat"></a>


```json
{
  "updated_at": "2017-02-12T15:19:21-02:00"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|updated_at|string(datetime)|false|No description|


<h2 id="tocSpaging">Paging</h2>


<a id="schemapaging"></a>


```json
{
  "total": 100,
  "offset": 0,
  "limit": 20
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|total|integer|false|No description|
|offset|integer|false|No description|
|limit|integer|false|No description|


<h2 id="tocSerror">Error</h2>


<a id="schemaerror"></a>


```json
{
  "code": "string",
  "message": "string"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|code|string|true|No description|
|message|string|true|No description|


