---
title: JTheta API v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="jtheta-api">JTheta API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

REST API for creating projects, uploading datasets, assigning annotations, and exporting data on the JTheta platform.

Base URLs:

* <a href="https://api.jtheta.ai">https://api.jtheta.ai</a>

<h1 id="jtheta-api-default">Default</h1>

## get__validate_key_

> Code samples

```shell
# You can also use wget
curl -X GET https://api.jtheta.ai/validate_key/

```

```http
GET https://api.jtheta.ai/validate_key/ HTTP/1.1
Host: api.jtheta.ai

```

```javascript

fetch('https://api.jtheta.ai/validate_key/',
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

result = RestClient.get 'https://api.jtheta.ai/validate_key/',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://api.jtheta.ai/validate_key/')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.jtheta.ai/validate_key/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/validate_key/");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.jtheta.ai/validate_key/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /validate_key/`

*Validate API key*

<h3 id="get__validate_key_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Valid API key|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Invalid or missing API key|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__create_project_

> Code samples

```shell
# You can also use wget
curl -X POST https://api.jtheta.ai/create_project/ \
  -H 'Content-Type: application/json'

```

```http
POST https://api.jtheta.ai/create_project/ HTTP/1.1
Host: api.jtheta.ai
Content-Type: application/json

```

```javascript
const inputBody = '{
  "project_title": "string",
  "project_category": "string"
}';
const headers = {
  'Content-Type':'application/json'
};

fetch('https://api.jtheta.ai/create_project/',
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
  'Content-Type' => 'application/json'
}

result = RestClient.post 'https://api.jtheta.ai/create_project/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('https://api.jtheta.ai/create_project/', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.jtheta.ai/create_project/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/create_project/");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.jtheta.ai/create_project/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /create_project/`

*Create a new project*

> Body parameter

```json
{
  "project_title": "string",
  "project_category": "string"
}
```

<h3 id="post__create_project_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» project_title|body|string|true|none|
|» project_category|body|string|true|none|

<h3 id="post__create_project_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Project created|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__create_dataset_

> Code samples

```shell
# You can also use wget
curl -X POST https://api.jtheta.ai/create_dataset/ \
  -H 'Content-Type: multipart/form-data'

```

```http
POST https://api.jtheta.ai/create_dataset/ HTTP/1.1
Host: api.jtheta.ai
Content-Type: multipart/form-data

```

```javascript
const inputBody = '{
  "dataset_name": "string",
  "project_name": "string",
  "license": "string",
  "images": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'multipart/form-data'
};

fetch('https://api.jtheta.ai/create_dataset/',
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
  'Content-Type' => 'multipart/form-data'
}

result = RestClient.post 'https://api.jtheta.ai/create_dataset/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data'
}

r = requests.post('https://api.jtheta.ai/create_dataset/', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'multipart/form-data',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.jtheta.ai/create_dataset/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/create_dataset/");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.jtheta.ai/create_dataset/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /create_dataset/`

*Create a dataset and upload images*

> Body parameter

```yaml
dataset_name: string
project_name: string
license: string
images:
  - string

```

<h3 id="post__create_dataset_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» dataset_name|body|string|true|none|
|» project_name|body|string|true|none|
|» license|body|string|false|none|
|» images|body|[string]|true|none|

<h3 id="post__create_dataset_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Dataset created and images uploaded|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__upload_images_to_dataset_

> Code samples

```shell
# You can also use wget
curl -X POST https://api.jtheta.ai/upload_images_to_dataset/ \
  -H 'Content-Type: multipart/form-data'

```

```http
POST https://api.jtheta.ai/upload_images_to_dataset/ HTTP/1.1
Host: api.jtheta.ai
Content-Type: multipart/form-data

```

```javascript
const inputBody = '{
  "dataset_id": 0,
  "project_name": "string",
  "images": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'multipart/form-data'
};

fetch('https://api.jtheta.ai/upload_images_to_dataset/',
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
  'Content-Type' => 'multipart/form-data'
}

result = RestClient.post 'https://api.jtheta.ai/upload_images_to_dataset/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data'
}

r = requests.post('https://api.jtheta.ai/upload_images_to_dataset/', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'multipart/form-data',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.jtheta.ai/upload_images_to_dataset/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/upload_images_to_dataset/");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"multipart/form-data"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.jtheta.ai/upload_images_to_dataset/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /upload_images_to_dataset/`

*Upload more images to a dataset*

> Body parameter

```yaml
dataset_id: 0
project_name: string
images:
  - string

```

<h3 id="post__upload_images_to_dataset_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» dataset_id|body|integer|true|none|
|» project_name|body|string|true|none|
|» images|body|[string]|true|none|

<h3 id="post__upload_images_to_dataset_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Images uploaded successfully|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__request_annotation_

> Code samples

```shell
# You can also use wget
curl -X POST https://api.jtheta.ai/request_annotation/ \
  -H 'Content-Type: application/json'

```

```http
POST https://api.jtheta.ai/request_annotation/ HTTP/1.1
Host: api.jtheta.ai
Content-Type: application/json

```

```javascript
const inputBody = '{
  "dataset_id": 0,
  "project_name": "string",
  "assigned_annotator": "string",
  "assigned_reviewer": "string",
  "labels": [
    {
      "label": "string",
      "type": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json'
};

fetch('https://api.jtheta.ai/request_annotation/',
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
  'Content-Type' => 'application/json'
}

result = RestClient.post 'https://api.jtheta.ai/request_annotation/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('https://api.jtheta.ai/request_annotation/', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.jtheta.ai/request_annotation/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/request_annotation/");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.jtheta.ai/request_annotation/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /request_annotation/`

*Assign annotators and reviewers to a dataset*

> Body parameter

```json
{
  "dataset_id": 0,
  "project_name": "string",
  "assigned_annotator": "string",
  "assigned_reviewer": "string",
  "labels": [
    {
      "label": "string",
      "type": "string"
    }
  ]
}
```

<h3 id="post__request_annotation_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» dataset_id|body|integer|false|none|
|» project_name|body|string|false|none|
|» assigned_annotator|body|string|false|none|
|» assigned_reviewer|body|string|false|none|
|» labels|body|[object]|false|none|
|»» label|body|string|false|none|
|»» type|body|string|false|none|

<h3 id="post__request_annotation_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Annotations assigned|None|

<aside class="success">
This operation does not require authentication
</aside>

## get__get_annotation_status_{project_title}_

> Code samples

```shell
# You can also use wget
curl -X GET https://api.jtheta.ai/get_annotation_status/{project_title}/

```

```http
GET https://api.jtheta.ai/get_annotation_status/{project_title}/ HTTP/1.1
Host: api.jtheta.ai

```

```javascript

fetch('https://api.jtheta.ai/get_annotation_status/{project_title}/',
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

result = RestClient.get 'https://api.jtheta.ai/get_annotation_status/{project_title}/',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://api.jtheta.ai/get_annotation_status/{project_title}/')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.jtheta.ai/get_annotation_status/{project_title}/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/get_annotation_status/{project_title}/");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.jtheta.ai/get_annotation_status/{project_title}/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /get_annotation_status/{project_title}/`

*Get annotation progress status*

<h3 id="get__get_annotation_status_{project_title}_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_title|path|string|true|none|

<h3 id="get__get_annotation_status_{project_title}_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status info|None|

<aside class="success">
This operation does not require authentication
</aside>

## post__delete_project_

> Code samples

```shell
# You can also use wget
curl -X POST https://api.jtheta.ai/delete_project/ \
  -H 'Content-Type: application/json'

```

```http
POST https://api.jtheta.ai/delete_project/ HTTP/1.1
Host: api.jtheta.ai
Content-Type: application/json

```

```javascript
const inputBody = '{
  "project_title": "string"
}';
const headers = {
  'Content-Type':'application/json'
};

fetch('https://api.jtheta.ai/delete_project/',
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
  'Content-Type' => 'application/json'
}

result = RestClient.post 'https://api.jtheta.ai/delete_project/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('https://api.jtheta.ai/delete_project/', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.jtheta.ai/delete_project/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/delete_project/");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.jtheta.ai/delete_project/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /delete_project/`

*Delete a project and its related data*

> Body parameter

```json
{
  "project_title": "string"
}
```

<h3 id="post__delete_project_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» project_title|body|string|false|none|

<h3 id="post__delete_project_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Project deleted successfully|None|

<aside class="success">
This operation does not require authentication
</aside>

## get__api_export_download

> Code samples

```shell
# You can also use wget
curl -X GET https://api.jtheta.ai/api/export/download?key=string

```

```http
GET https://api.jtheta.ai/api/export/download?key=string HTTP/1.1
Host: api.jtheta.ai

```

```javascript

fetch('https://api.jtheta.ai/api/export/download?key=string',
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

result = RestClient.get 'https://api.jtheta.ai/api/export/download',
  params: {
  'key' => 'string'
}

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://api.jtheta.ai/api/export/download', params={
  'key': 'string'
})

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.jtheta.ai/api/export/download', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.jtheta.ai/api/export/download?key=string");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.jtheta.ai/api/export/download", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/export/download`

*Get dataset info & dataset download URL*

<h3 id="get__api_export_download-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|key|query|string|true|none|

<h3 id="get__api_export_download-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|302|[Found](https://tools.ietf.org/html/rfc7231#section-6.4.3)|Dataset info & dataset download URL|None|

<aside class="success">
This operation does not require authentication
</aside>

