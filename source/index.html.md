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

Primaccess API

Base URLs:

* <a href="https://primaccess-179015.appspot.com/">https://primaccess-179015.appspot.com/</a>





# Accounts

Everything about your accounts

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
» created_at|string|false|No description
» updated_at|string(datetime)|false|No description
total|integer|false|No description
offset|integer|false|No description
limit|integer|false|No description



<aside class="success">
This operation does not require authentication
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
  "phone": "0601020304"
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
  "phone": "0601020304"
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


> Example responses

```json
{
  "reference": "AAAA-BBBB",
  "last_name": "Doe",
  "first_name": "John",
  "email": "john.doe@gmail.com",
  "phone": "0601020304"
}
```
<h3 id="createAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created account|[Account](#schemaaccount)

<aside class="success">
This operation does not require authentication
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
  "phone": "0601020304"
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



<aside class="success">
This operation does not require authentication
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

<aside class="success">
This operation does not require authentication
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

<aside class="success">
This operation does not require authentication
</aside>

## getBadgesByAccountId

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

<h3 id="getBadgesByAccountId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Account uuid


<h3 id="getBadgesByAccountId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="success">
This operation does not require authentication
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

<aside class="success">
This operation does not require authentication
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

<aside class="success">
This operation does not require authentication
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

<aside class="success">
This operation does not require authentication
</aside>

# Cards

Everything about your cards

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

<aside class="success">
This operation does not require authentication
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

<aside class="success">
This operation does not require authentication
</aside>

## getOwnersByCardId

> Code samples

```shell
# You can also use wget
curl -X GET https://primaccess-179015.appspot.com/cards/{id}/owners

```

```http
GET https://primaccess-179015.appspot.com/cards/{id}/owners HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards/{id}/owners',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards/{id}/owners',
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


result = RestClient.get 'https://primaccess-179015.appspot.com/cards/{id}/owners',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://primaccess-179015.appspot.com/cards/{id}/owners', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards/{id}/owners");
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

`GET /cards/{id}/owners`

*Get owners for a card*

<h3 id="getOwnersByCardId-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Card uuid


<h3 id="getOwnersByCardId-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="success">
This operation does not require authentication
</aside>

## assignCardOnAccount

> Code samples

```shell
# You can also use wget
curl -X PUT https://primaccess-179015.appspot.com/cards/{id}/owner

```

```http
PUT https://primaccess-179015.appspot.com/cards/{id}/owner HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards/{id}/owner',
  method: 'put',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards/{id}/owner',
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


result = RestClient.put 'https://primaccess-179015.appspot.com/cards/{id}/owner',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.put('https://primaccess-179015.appspot.com/cards/{id}/owner', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards/{id}/owner");
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

`PUT /cards/{id}/owner`

*Assign card for an account*

<h3 id="assignCardOnAccount-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Card uuid


<h3 id="assignCardOnAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="success">
This operation does not require authentication
</aside>

## removeCardOnAccount

> Code samples

```shell
# You can also use wget
curl -X DELETE https://primaccess-179015.appspot.com/cards/{id}/owner

```

```http
DELETE https://primaccess-179015.appspot.com/cards/{id}/owner HTTP/1.1
Host: primaccess-179015.appspot.com


```

```javascript

$.ajax({
  url: 'https://primaccess-179015.appspot.com/cards/{id}/owner',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://primaccess-179015.appspot.com/cards/{id}/owner',
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


result = RestClient.delete 'https://primaccess-179015.appspot.com/cards/{id}/owner',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://primaccess-179015.appspot.com/cards/{id}/owner', params={

)

print r.json()
```

```java
URL obj = new URL("https://primaccess-179015.appspot.com/cards/{id}/owner");
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

`DELETE /cards/{id}/owner`

*Remove card for an account*

<h3 id="removeCardOnAccount-parameters">Parameters</h3>

Parameter|In|Type|Required|Description
---|---|---|---|---|
id|path|string|true|Card uuid


<h3 id="removeCardOnAccount-responses">Responses</h3>

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account succesfully deleted|None

<aside class="success">
This operation does not require authentication
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
  "phone": "0601020304"
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



## Wallet

<a name="schemawallet"></a>

```json
{
  "name": "Golf store",
  "balance": "10.50"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|No description
balance|number|false|No description



## Card

<a name="schemacard"></a>

```json
{
  "tag": "040F1848D7581"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
tag|string|false|No description



## Group

<a name="schemagroup"></a>

```json
{
  "name": "Professionals",
  "access": [
    "00-24"
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|No description
access|[string]|false|No description



## Endpoint

<a name="schemaendpoint"></a>

```json
{
  "reference": "string",
  "name": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
reference|string|false|No description
name|string|false|No description



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
  "endpoint": {
    "reference": "string",
    "name": "string"
  },
  "name": "string",
  "amount": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
endpoint|[Endpoint](#schemaendpoint)|false|No description
» reference|string|false|No description
» name|string|false|No description
name|string|false|No description
amount|number|false|No description



## CardOwner

<a name="schemacardowner"></a>

```json
{
  "card": {
    "tag": "040F1848D7581"
  },
  "account": {
    "reference": "AAAA-BBBB",
    "last_name": "Doe",
    "first_name": "John",
    "email": "john.doe@gmail.com",
    "phone": "0601020304"
  },
  "assign_on": "2017-02-12T15:19:21+01:00"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
card|[Card](#schemacard)|false|No description
» tag|string|false|No description
account|[Account](#schemaaccount)|false|No description
» reference|string|false|No description
» last_name|string|false|No description
» first_name|string|false|No description
» email|string|false|No description
» phone|string|false|No description
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





