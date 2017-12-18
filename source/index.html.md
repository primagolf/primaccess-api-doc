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

# Primaccess API v1.0

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

# Dates and times
All dates and times in the API are in **UTC**. This means that when submitting dates and times in your requests your payload should include date/time in **UTC**.
When processing dates and times in responses from the API you should translate them to the local time of the associated outlet.

Base URLs:

* <a href="https://primaccess-179015.appspot.com/">https://primaccess-179015.appspot.com/</a>





# Authentication


* API Key
    - Parameter Name: **X-API-Key**, in: header. 



# Accounts

## getAccounts

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/accounts \
  -H 'Accept: application/json'

```

```http
GET https://primaccess-179015.appspot.com/accounts HTTP/1.1
Host: primaccess-179015.appspot.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts',
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

fetch('https://primaccess-179015.appspot.com/accounts',
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

result = RestClient.get 'https://primaccess-179015.appspot.com/accounts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://primaccess-179015.appspot.com/accounts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts");
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

*Search for accounts*

<h3 id="getAccounts-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
reference|query|string|false|Customer reference
last_name|query|string|false|Last name
first_name|query|string|false|First name
email|query|string|false|Email
phone|query|string|false|Phone
sort|query|string|false|List of fields for sorting
range|query|string|false|The numbers of items to return (offset-limit)


> Example responses

```json
{
  "total": 100,
  "offset": 0,
  "limit": 20
}
```
<h3 id="getAccounts-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Accounts list|Inline
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|No description|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No description|None

<h3 id="getAccounts-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
undefined|Unknown|false|No description
data|[Unknown]|false|No description
» id|string|true|No description
» reference|string|false|No description
» last_name|string|false|No description
» first_name|string|false|No description
» email|string|false|No description
» phone|string|false|No description
» is_superuser|boolean|false|No description
» created_at|string|false|No description
» updated_at|string(datetime)|false|No description
total|integer|false|No description
offset|integer|false|No description
limit|integer|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## createAccount

> Code samples

```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com/accounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://primaccess-179015.appspot.com/accounts HTTP/1.1
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
  url: 'https://primaccess-179015.appspot.com/accounts',
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

fetch('https://primaccess-179015.appspot.com/accounts',
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

result = RestClient.post 'https://primaccess-179015.appspot.com/accounts',
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

r = requests.post('https://primaccess-179015.appspot.com/accounts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts");
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

*Create an account*

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

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[Account](#schemaaccount)|true|Customer Reference
» reference|body|string|false|No description
» last_name|body|string|false|No description
» first_name|body|string|false|No description
» email|body|string|false|No description
» phone|body|string|false|No description
» is_superuser|body|boolean|false|No description


> Example responses

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
<h3 id="createAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created account|[Account](#schemaaccount)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getAccountById

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/accounts/{id} \
  -H 'Accept: application/json'

```

```http
GET https://primaccess-179015.appspot.com/accounts/{id} HTTP/1.1
Host: primaccess-179015.appspot.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts/{id}',
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

fetch('https://primaccess-179015.appspot.com/accounts/{id}',
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

result = RestClient.get 'https://primaccess-179015.appspot.com/accounts/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://primaccess-179015.appspot.com/accounts/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts/{id}");
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

`GET /accounts/{id}`

*Get an existing account*

<h3 id="getAccountById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


> Example responses

```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304",
  "is_superuser": false
}
```
<h3 id="getAccountById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully updated|Inline

<h3 id="getAccountById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
undefined|Unknown|false|No description
id|string|true|No description
reference|string|false|No description
last_name|string|false|No description
first_name|string|false|No description
email|string|false|No description
phone|string|false|No description
is_superuser|boolean|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## updateAccount

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/accounts/{id}

```

```http
PUT https://primaccess-179015.appspot.com/accounts/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts/{id}',
  method: 'put',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/accounts/{id}',
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


result = RestClient.put 'https://primaccess-179015.appspot.com/accounts/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.put('https://primaccess-179015.appspot.com/accounts/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts/{id}");
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

`PUT /accounts/{id}`

*Update an existing account*

<h3 id="updateAccount-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


<h3 id="updateAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Account succesfully updated|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## deleteAccount

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/accounts/{id}

```

```http
DELETE https://primaccess-179015.appspot.com/accounts/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts/{id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/accounts/{id}',
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


result = RestClient.delete 'https://primaccess-179015.appspot.com/accounts/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://primaccess-179015.appspot.com/accounts/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts/{id}");
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

`DELETE /accounts/{id}`

*Delete an existing account*

<h3 id="deleteAccount-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


<h3 id="deleteAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getCardsByAccountId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/accounts/{id}/cards

```

```http
GET https://primaccess-179015.appspot.com/accounts/{id}/cards HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts/{id}/cards',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/accounts/{id}/cards',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/accounts/{id}/cards',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/accounts/{id}/cards', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts/{id}/cards");
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

`GET /accounts/{id}/cards`

*Get cards for an account*

<h3 id="getCardsByAccountId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Account uuid


<h3 id="getCardsByAccountId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getWalletsByAccountId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/accounts/{id}/wallets

```

```http
GET https://primaccess-179015.appspot.com/accounts/{id}/wallets HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts/{id}/wallets',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/accounts/{id}/wallets',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/accounts/{id}/wallets',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/accounts/{id}/wallets', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts/{id}/wallets");
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

`GET /accounts/{id}/wallets`

*Get wallets for an account*

<h3 id="getWalletsByAccountId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Account uuid


<h3 id="getWalletsByAccountId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getTransactionsByAccountId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/accounts/{id}/transactions

```

```http
GET https://primaccess-179015.appspot.com/accounts/{id}/transactions HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts/{id}/transactions',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/accounts/{id}/transactions',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/accounts/{id}/transactions',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/accounts/{id}/transactions', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts/{id}/transactions");
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

`GET /accounts/{id}/transactions`

*Get transactions for an account*

<h3 id="getTransactionsByAccountId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Account uuid


<h3 id="getTransactionsByAccountId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getMovesByAccountId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/accounts/{id}/moves

```

```http
GET https://primaccess-179015.appspot.com/accounts/{id}/moves HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/accounts/{id}/moves',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/accounts/{id}/moves',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/accounts/{id}/moves',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/accounts/{id}/moves', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/accounts/{id}/moves");
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

`GET /accounts/{id}/moves`

*Get moves for an account*

<h3 id="getMovesByAccountId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Account uuid


<h3 id="getMovesByAccountId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Wallets

## createWallet

> Code samples

```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com/wallets \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://primaccess-179015.appspot.com/wallets HTTP/1.1
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
  url: 'https://primaccess-179015.appspot.com/wallets',
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
  "balance": "10.50",
  "practice_availability": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('https://primaccess-179015.appspot.com/wallets',
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

result = RestClient.post 'https://primaccess-179015.appspot.com/wallets',
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

r = requests.post('https://primaccess-179015.appspot.com/wallets', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets");
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

*Create a wallet*

> Body parameter

```json
{
  "name": "Golf store",
  "balance": "10.50",
  "practice_availability": true
}
```
<h3 id="createWallet-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[Wallet](#schemawallet)|true|Wallet object
» name|body|string|false|No description
» balance|body|number|false|No description
» practice_availability|body|boolean|false|No description


> Example responses

```json
{
  "name": "Golf store",
  "balance": "10.50",
  "practice_availability": true
}
```
<h3 id="createWallet-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created wallet|[Wallet](#schemawallet)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getWalletById

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/wallets/{id} \
  -H 'Accept: application/json'

```

```http
GET https://primaccess-179015.appspot.com/wallets/{id} HTTP/1.1
Host: primaccess-179015.appspot.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://primaccess-179015.appspot.com/wallets/{id}',
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

fetch('https://primaccess-179015.appspot.com/wallets/{id}',
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

result = RestClient.get 'https://primaccess-179015.appspot.com/wallets/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://primaccess-179015.appspot.com/wallets/{id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets/{id}");
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

`GET /wallets/{id}`

*Get an existing wallet*

<h3 id="getWalletById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


> Example responses

```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304",
  "is_superuser": false
}
```
<h3 id="getWalletById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Wallet succesfully updated|Inline

<h3 id="getWalletById-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
undefined|Unknown|false|No description
id|string|true|No description
reference|string|false|No description
last_name|string|false|No description
first_name|string|false|No description
email|string|false|No description
phone|string|false|No description
is_superuser|boolean|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## updateWallet

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/wallets/{id}

```

```http
PUT https://primaccess-179015.appspot.com/wallets/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/wallets/{id}',
  method: 'put',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/wallets/{id}',
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


result = RestClient.put 'https://primaccess-179015.appspot.com/wallets/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.put('https://primaccess-179015.appspot.com/wallets/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets/{id}");
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

`PUT /wallets/{id}`

*Update an existing wallet*

<h3 id="updateWallet-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


<h3 id="updateWallet-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Wallet succesfully updated|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## deleteWallet

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/wallets/{id}

```

```http
DELETE https://primaccess-179015.appspot.com/wallets/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/wallets/{id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/wallets/{id}',
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


result = RestClient.delete 'https://primaccess-179015.appspot.com/wallets/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://primaccess-179015.appspot.com/wallets/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets/{id}");
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

`DELETE /wallets/{id}`

*Delete an existing wallet*

<h3 id="deleteWallet-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


<h3 id="deleteWallet-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Wallet succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getAccountsByWalletId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/wallets/{id}/accounts \
  -H 'Accept: application/json'

```

```http
GET https://primaccess-179015.appspot.com/wallets/{id}/accounts HTTP/1.1
Host: primaccess-179015.appspot.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://primaccess-179015.appspot.com/wallets/{id}/accounts',
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

fetch('https://primaccess-179015.appspot.com/wallets/{id}/accounts',
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

result = RestClient.get 'https://primaccess-179015.appspot.com/wallets/{id}/accounts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://primaccess-179015.appspot.com/wallets/{id}/accounts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets/{id}/accounts");
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

`GET /wallets/{id}/accounts`

*Get accounts for an existing wallet*

<h3 id="getAccountsByWalletId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


> Example responses

```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Golf store",
  "balance": "10.50",
  "practice_availability": true
}
```
<h3 id="getAccountsByWalletId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Wallet succesfully updated|Inline

<h3 id="getAccountsByWalletId-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
undefined|Unknown|false|No description
id|string|true|No description
name|string|false|No description
balance|number|false|No description
practice_availability|boolean|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getTransactionsByWalletId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/wallets/{id}/transactions \
  -H 'Accept: application/json'

```

```http
GET https://primaccess-179015.appspot.com/wallets/{id}/transactions HTTP/1.1
Host: primaccess-179015.appspot.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://primaccess-179015.appspot.com/wallets/{id}/transactions',
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

fetch('https://primaccess-179015.appspot.com/wallets/{id}/transactions',
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

result = RestClient.get 'https://primaccess-179015.appspot.com/wallets/{id}/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://primaccess-179015.appspot.com/wallets/{id}/transactions', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets/{id}/transactions");
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

`GET /wallets/{id}/transactions`

*Get transactions for an existing wallet*

<h3 id="getTransactionsByWalletId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


> Example responses

```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Golf store",
  "balance": "10.50",
  "practice_availability": true
}
```
<h3 id="getTransactionsByWalletId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Wallet succesfully updated|Inline

<h3 id="getTransactionsByWalletId-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
undefined|Unknown|false|No description
id|string|true|No description
name|string|false|No description
balance|number|false|No description
practice_availability|boolean|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## linkAccountToWallet

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id} \
  -H 'Accept: application/json'

```

```http
PUT https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}',
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

fetch('https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}',
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

result = RestClient.put 'https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}");
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

*Link an account to a wallet*

<h3 id="linkAccountToWallet-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
wallet_id|path|string|true|No description
account_id|path|string|true|No description


> Example responses

```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Golf store",
  "balance": "10.50",
  "practice_availability": true
}
```
<h3 id="linkAccountToWallet-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Wallet succesfully updated|Inline

<h3 id="linkAccountToWallet-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
undefined|Unknown|false|No description
id|string|true|No description
name|string|false|No description
balance|number|false|No description
practice_availability|boolean|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## unlinkAccountFromWallet

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id} \
  -H 'Accept: application/json'

```

```http
DELETE https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}',
  method: 'delete',

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

fetch('https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}',
{
  method: 'DELETE',

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

result = RestClient.delete 'https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/wallets/{wallet_id}/accounts/{account_id}");
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

*Unlink an account from a wallet*

<h3 id="unlinkAccountFromWallet-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
wallet_id|path|string|true|No description
account_id|path|string|true|No description


> Example responses

```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408",
  "name": "Golf store",
  "balance": "10.50",
  "practice_availability": true
}
```
<h3 id="unlinkAccountFromWallet-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Wallet succesfully updated|Inline

<h3 id="unlinkAccountFromWallet-responseschema">Response Schema</h3>

Status Code **200**

Name|Type|Required|Description
---|---|---|---|---|
undefined|Unknown|false|No description
id|string|true|No description
name|string|false|No description
balance|number|false|No description
practice_availability|boolean|false|No description



<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Cards

## getCards

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/cards

```

```http
GET https://primaccess-179015.appspot.com/cards HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/cards',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/cards', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards");
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

`GET /cards`

*Get cards*

<h3 id="getCards-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getCardById

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/cards/{id}

```

```http
GET https://primaccess-179015.appspot.com/cards/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards/{id}',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards/{id}',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/cards/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/cards/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards/{id}");
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

`GET /cards/{id}`

*Get cards for an account*

<h3 id="getCardById-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Card uuid


<h3 id="getCardById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getOwnersByCardId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/cards/{card_id}/accounts

```

```http
GET https://primaccess-179015.appspot.com/cards/{card_id}/accounts HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards/{card_id}/accounts',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards/{card_id}/accounts',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/cards/{card_id}/accounts',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/cards/{card_id}/accounts', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards/{card_id}/accounts");
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

*Get owners for a card*

<h3 id="getOwnersByCardId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
card_id|path|string|true|Card uuid


<h3 id="getOwnersByCardId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## assignCardOnAccount

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}

```

```http
PUT https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}',
  method: 'put',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}',
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


result = RestClient.put 'https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.put('https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}");
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

*Assign card for an account*

<h3 id="assignCardOnAccount-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
card_id|path|string|true|Card uuid
account_id|path|string|true|Account uuid


<h3 id="assignCardOnAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Card succesfully assigned|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## removeCardOnAccount

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}

```

```http
DELETE https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}',
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


result = RestClient.delete 'https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards/{card_id}/accounts/{account_id}");
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

*Remove card for an account*

<h3 id="removeCardOnAccount-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
card_id|path|string|true|Card uuid
account_id|path|string|true|Account uuid


<h3 id="removeCardOnAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Card succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Groups

## getGroups

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/groups/

```

```http
GET https://primaccess-179015.appspot.com/groups/ HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/groups/',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/groups/',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/groups/',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/groups/', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/groups/");
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

*Update an existing account*

<h3 id="getGroups-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Account succesfully updated|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## createGroup

> Code samples

```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com/groups/

```

```http
POST https://primaccess-179015.appspot.com/groups/ HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/groups/',
  method: 'post',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/groups/',
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


result = RestClient.post 'https://primaccess-179015.appspot.com/groups/',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.post('https://primaccess-179015.appspot.com/groups/', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/groups/");
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

*Delete an existing account*

<h3 id="createGroup-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## updateGroup

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/groups/{group_id}

```

```http
PUT https://primaccess-179015.appspot.com/groups/{group_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/groups/{group_id}',
  method: 'put',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/groups/{group_id}',
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


result = RestClient.put 'https://primaccess-179015.appspot.com/groups/{group_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.put('https://primaccess-179015.appspot.com/groups/{group_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/groups/{group_id}");
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

*Update an existing account*

<h3 id="updateGroup-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
group_id|path|string|true|No description


<h3 id="updateGroup-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Account succesfully updated|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## deleteGroup

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/groups/{group_id}

```

```http
DELETE https://primaccess-179015.appspot.com/groups/{group_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/groups/{group_id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/groups/{group_id}',
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


result = RestClient.delete 'https://primaccess-179015.appspot.com/groups/{group_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://primaccess-179015.appspot.com/groups/{group_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/groups/{group_id}");
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

*Delete an existing account*

<h3 id="deleteGroup-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
group_id|path|string|true|No description


<h3 id="deleteGroup-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Account succesfully deleted|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## linkAccountToGroup

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}

```

```http
GET https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}");
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

`GET /groups/{group_id}/accounts/{account_id}`

*Link an account to a group*

<h3 id="linkAccountToGroup-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
group_id|path|string|true|No description
account_id|path|string|true|No description


<h3 id="linkAccountToGroup-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## unlinkAccountFromGroup

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}

```

```http
DELETE https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}',
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


result = RestClient.delete 'https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/groups/{group_id}/accounts/{account_id}");
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

*Unlink an account from a group*

<h3 id="unlinkAccountFromGroup-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
group_id|path|string|true|No description
account_id|path|string|true|No description


<h3 id="unlinkAccountFromGroup-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Transactions

## getTransactionTypes

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/transactions/types

```

```http
GET https://primaccess-179015.appspot.com/transactions/types HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions/types',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions/types',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/transactions/types',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/transactions/types', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions/types");
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

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## createTransactionType

> Code samples

```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com/transactions/types

```

```http
POST https://primaccess-179015.appspot.com/transactions/types HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions/types',
  method: 'post',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions/types',
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


result = RestClient.post 'https://primaccess-179015.appspot.com/transactions/types',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.post('https://primaccess-179015.appspot.com/transactions/types', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions/types");
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

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getTransactionTypeById

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}

```

```http
GET https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}");
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

Parameter|In|Type|Required|Description
---|---|---|---|---|
transaction_type_id|path|string|true|No description


<h3 id="getTransactionTypeById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## updateTransactionType

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}

```

```http
PUT https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
  method: 'put',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
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


result = RestClient.put 'https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.put('https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}");
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

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## deleteTransactionType

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}

```

```http
DELETE https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
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


result = RestClient.delete 'https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions/types/{transaction_type_id}");
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

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## searchTransactions

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/transactions

```

```http
GET https://primaccess-179015.appspot.com/transactions HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/transactions',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/transactions', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions");
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

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## createTransaction

> Code samples

```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com/transactions

```

```http
POST https://primaccess-179015.appspot.com/transactions HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions',
  method: 'post',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions',
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


result = RestClient.post 'https://primaccess-179015.appspot.com/transactions',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.post('https://primaccess-179015.appspot.com/transactions', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions");
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

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getTransactionById

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/transactions/{id}

```

```http
GET https://primaccess-179015.appspot.com/transactions/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/transactions/{id}',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/transactions/{id}',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/transactions/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/transactions/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/transactions/{id}");
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

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


<h3 id="getTransactionById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Endpoints

## getEndpoints

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/endpoints

```

```http
GET https://primaccess-179015.appspot.com/endpoints HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/endpoints',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/endpoints',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/endpoints',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/endpoints', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/endpoints");
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

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getEndpointById

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/endpoints/{id}

```

```http
PUT https://primaccess-179015.appspot.com/endpoints/{id} HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/endpoints/{id}',
  method: 'put',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/endpoints/{id}',
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


result = RestClient.put 'https://primaccess-179015.appspot.com/endpoints/{id}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.put('https://primaccess-179015.appspot.com/endpoints/{id}', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/endpoints/{id}");
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

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|No description


<h3 id="getEndpointById-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Access

## searchAccess

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/access

```

```http
GET https://primaccess-179015.appspot.com/access HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/access',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/access',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/access',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/access', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/access");
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

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## createAccess

> Code samples

```shell
# You can also use wget
curl -X POST https://primaccess-179015.appspot.com/access

```

```http
POST https://primaccess-179015.appspot.com/access HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/access',
  method: 'post',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/access',
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


result = RestClient.post 'https://primaccess-179015.appspot.com/access',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.post('https://primaccess-179015.appspot.com/access', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/access");
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

<h3 id="createAccess-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Miscellaneous

## searchMoves

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/moves

```

```http
GET https://primaccess-179015.appspot.com/moves HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/moves',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/moves',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/moves',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/moves', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/moves");
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

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## getAttendance

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/attendance

```

```http
GET https://primaccess-179015.appspot.com/attendance HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/attendance',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/attendance',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/attendance',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/attendance', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/attendance");
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

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Schemas

## Account

<a name="schemaaccount"></a>

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

Name|Type|Required|Description
---|---|---|---|
reference|string|false|No description
last_name|string|false|No description
first_name|string|false|No description
email|string|false|No description
phone|string|false|No description
is_superuser|boolean|false|No description



## Wallet

<a name="schemawallet"></a>

```json
{
  "name": "Golf store",
  "balance": "10.50",
  "practice_availability": true
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|No description
balance|number|false|No description
practice_availability|boolean|false|No description



## Group

<a name="schemagroup"></a>

```json
{
  "name": "Professionals"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|No description



## Endpoint

<a name="schemaendpoint"></a>

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

Name|Type|Required|Description
---|---|---|---|
name|string|false|No description
fee|number|false|No description
version|string|false|No description
last_boot_at|string(datetime)|false|No description
last_ntf_at|string(datetime)|false|No description



## Transaction

<a name="schematransaction"></a>

```json
{
  "wallet_id": "string",
  "reference": "string",
  "name": "string",
  "amount": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
wallet_id|string|false|No description
reference|string|false|No description
name|string|false|No description
amount|number|false|No description



## Move

<a name="schemamove"></a>

```json
{
  "endpoint_id": "string",
  "card_owner_id": "string",
  "amount": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
endpoint_id|string|false|Endpoint uuid
card_owner_id|string|false|CardOwner uuid
amount|number|false|Move swipe amount



## CardOwner

<a name="schemacardowner"></a>

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

Name|Type|Required|Description
---|---|---|---|
account|[Account](#schemaaccount)|false|No description
» reference|string|false|No description
» last_name|string|false|No description
» first_name|string|false|No description
» email|string|false|No description
» phone|string|false|No description
» is_superuser|boolean|false|No description
assign_on|string|false|No description



## Id

<a name="schemaid"></a>

```json
{
  "id": "902357bd-c9ec-11e7-ad91-00155d011408"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string|true|No description



## CreatedAt

<a name="schemacreatedat"></a>

```json
{
  "created_at": "2017-02-12T15:19:21+01:00"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
created_at|string|false|No description



## UpdatedAt

<a name="schemaupdatedat"></a>

```json
{
  "updated_at": "2017-02-12T15:19:21-02:00"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
updated_at|string(datetime)|false|No description



## Paging

<a name="schemapaging"></a>

```json
{
  "total": 100,
  "offset": 0,
  "limit": 20
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
total|integer|false|No description
offset|integer|false|No description
limit|integer|false|No description



## Error

<a name="schemaerror"></a>

```json
{
  "code": "string",
  "message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|true|No description
message|string|true|No description





