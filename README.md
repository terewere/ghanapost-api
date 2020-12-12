# UNOFFICAL GHANA POST GPS REST API
Get Location using digital address and GPS Coordinates (Latitud and Longitude)
[documentation](https://api.sourcecodegh.com/v1/documentation)

# Description
This API allows developers to get location details in Ghana using digital address or GPS coordinates.

# QUICK START - Limited Scope
## GET/POST
Get location data Ghana Post API using Digital Address or GPS coordinates(LAT & LONG).

## Obtaining Location
To quickly obtain location details without signing up for the Access Token, see an example below.
**Note:** you can only access 5 location details in 5 minutes.

### JavaScript (axios)

``
USING DIGITAL ADDRESS
https://api.sourcecodegh.com/v1/gps/trial/GPSName

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://api.sourcecodegh.com/v1/gps/trial/GN09206216',
  headers: { 
    'Accept': 'application/json', 
    'Authorization': 'Bearer [access_token_here]'
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});


//USING GPS COORDINATES (LATITUDE & LONGITUDE)
//https://api.sourcecodegh.com/v1/gps/trial/Lati/Longi

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://api.sourcecodegh.com/v1/gps/trial/5.8142835999999996/0.0746767',
  headers: { 
    'Accept': 'application/json', 
    'Authorization': 'Bearer [access_token_here]'
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
  ``

  ###### PHP (curl)

``
 //USING DIGITAL ADDRESS
 //https://api.sourcecodegh.com/v1/gps/trial/GPSName


  $curl = curl_init();
  curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.sourcecodegh.com/v1/gps/trial/GN09206216',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/json',
    'Authorization: Bearer [access_token_here]'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;



//USING GPS COORDINATES (LATITUDE & LONGITUDE)
//https://api.sourcecodegh.com/v1/gps/trial/Lati/Longi


  $curl = curl_init();
  curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.sourcecodegh.com/v1/gps/trial/5.8142835999999996/0.0746767',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/json',
    'Authorization: Bearer [access_token_here]'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
``

###### Dart
``
//USING DIGITAL ADDRESS
//https://api.sourcecodegh.com/v1/gps/trial/GPSName


var headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer [access_token_here]'

};
var request = http.Request('GET', Uri.parse('https://api.sourcecodegh.com/v1/gps/trial/GN09206216'));

request.headers.addAll(headers);

http.StreamedResponse response = await request.send();

if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
}
else {
  print(response.reasonPhrase);
}



//USING GPS COORDINATES (LATITUDE & LONGITUDE)
//https://api.sourcecodegh.com/v1/gps/trial/Lati/Longi


  var headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer [access_token_here]'

};
var request = http.Request('GET', Uri.parse('https://api.sourcecodegh.com/v1/gps/trial/5.8142835999999996/0.0746767'));

request.headers.addAll(headers);

http.StreamedResponse response = await request.send();

if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
}
else {
  print(response.reasonPhrase);
}
``

###### Pyython (http.client)
``
//USING DIGITAL ADDRESS
//https://api.sourcecodegh.com/v1/gps/trial/GPSName


import http.client

conn = http.client.HTTPSConnection("161.35.163.133")
payload = ''
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer [access_token_here]'
}
conn.request("GET", "/gps/trial/GN09206216", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))


//USING GPS COORDINATES (LATITUDE & LONGITUDE)
//https://api.sourcecodegh.com/v1/gps/trial/Lati/Longi


import http.client

conn = http.client.HTTPSConnection("161.35.163.133")
payload = ''
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer [access_token_here]'
}
conn.request("GET", "/gps/trial/5.8142835999999996/0.0746767", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))

``

# Setting up an Account
To access the API without LIMITATION, you need to create an account. This is required to prevent abuse of the API.
Setting up an account is compeletly FREE, simply sign up [Here](https://api.sourcecodegh.com/v1/register) . When you complete the signup form, a verification mail will be sent to you to verify your email. Upon successful verification, you will be able to generate client detail for accessing the API.


# Usage

## ACCESS TOKEN
#### /token - GET/POST

Used to generate token to access Ghana Post API.

To obtain an `access_token`, you need to generate a `client` id and `secret` from your dashoard. **[Sign in Here](/login)**

#### Obtaining Access Token
After generating client details, request for access token by calling our API with the client details, see an example below.

###### Javascript (axios)

``
var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://api.sourcecodegh.com/v1/gps/token?client='client_id_here'&secret='client_secret_here',
  headers: { 
    'Accept': 'application/json'
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

``

###### PHP (CURL)

``
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.sourcecodegh.com/v1/gps/token?client='client_id_here'&secret='client_secret_here',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/json'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

``

###### Dart 

``
var headers = {
  'Accept': 'application/json'
};
var request = http.Request('GET', Uri.parse('https://api.sourcecodegh.com/v1/gps/token?client='client_id_here'&secret='client_secret_here'));

request.headers.addAll(headers);

http.StreamedResponse response = await request.send();

if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
}
else {
  print(response.reasonPhrase);
}

``

###### Python(http.client)

``
import http.client

conn = http.client.HTTPSConnection("161.35.163.133")
payload = ''
headers = {
  'Accept': 'application/json'
}
conn.request("GET", "/gps/token?client='client_id_here'&secret='client_secret_here'", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))

``

## JSON RESPONSE
``
{
    "token_type": "Bearer",
    "expires_in": 31536000,
    "access_token": "[access_token]"
}
``

If the request is successful, an access token is returned as response. use it to access the Ghana Post API.


## GET LOCATION USING DIGITAL ADDRESS
/gps - GET/POST
get location data Ghana Post API using digital address.

Parameter: 
GPSName. the digital address. example: GN09206216

#### Obtaining Location
With the access token generated from the previous step, request for location info by calling our API with GPSName (Digital Address), see an example below.

###### Javascript (axios)

``

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://api.sourcecodegh.com/v1/gps?Action=GetLocation&GPSName=GN09206216',
  headers: { 
    'Accept': 'application/json', 
    'Authorization': 'Bearer [access_token_here]', 
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

``

###### PHP (CURL)

``
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.sourcecodegh.com/v1/gps?Action=GetLocation&GPSName=GN09206216',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/json',
    'Authorization: Bearer [access_token_here]'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

``


###### Dart

``

var headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer [access_token_here]'

};
var request = http.Request('GET', Uri.parse('https://api.sourcecodegh.com/v1/gps?Action=GetLocation&GPSName=GN09206216'));

request.headers.addAll(headers);

http.StreamedResponse response = await request.send();

if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
}
else {
  print(response.reasonPhrase);
}

``

###### Python(http.cient)

``

import http.client
import mimetypes
from codecs import encode

conn = http.client.HTTPSConnection("161.35.163.133")
boundary = ''
payload = ''
headers = {
  'Accept': 'application/json',
  'Authorization': ''Bearer [access_token_here]'
}
conn.request("GET", "/gps?Action=GetLocation&GPSName=GN09206216", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))

``

## JSON RESPONSE

``
{
    "CenterLatitude": 5.814259555768489,
    "CenterLongitude": 0.074672574122148,
    "NorthLat": 5.81428204422724,
    "NorthLong": 0.074650000108659,
    "SouthLat": 5.81423709788684,
    "SouthLong": 0.074650000108659,
    "EastLat": 5.81423709788684,
    "EastLong": 0.074694915872864,
    "WestLat": 5.81428204422724,
    "WestLong": 0.074694915872864,
    "GPSName": "GN09206216",
    "PostCode": "GN0920",
    "District": "Ningo Prampram",
    "Region": "Greater Accra",
    "Area": "BUERKO",
    "Street": ".[Unknown Street]",
    "PlaceName": ""
}

``

If the request is successful, the requested location info is returned as response.


## GET LOCATION USING GPS COORDINATES(LAT & LONG)
/gps - GET/POST
Get location data Ghana Post API using GPS coordinates(LAT & LONG).

To get location by GPS coordinate you need to generate access_token

Parameters: 
Lati. Latitude. example: 5.8142835999999996
Longi. Longitude. example: 0.0746767

#### Obtaining Location
With the access token generated from the previous step, request for location info by calling our API with GPS Coordinates (Latitude & Longitude), see an example below.

###### Javascript (axios)

``
var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://api.sourcecodegh.com/v1/gps?Action=GetGPSName&Lati=5.8142835999999996&Longi=0.0746767',
  headers: { 
    'Accept': 'application/json', 
    'Authorization': 'Bearer [access_token_here]'
   
  },
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

``

###### PHP (CURL)

``

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.sourcecodegh.com/v1/gps?Action=GetGPSName&Lati=5.8142835999999996&Longi=0.0746767',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Accept: application/json',
    'Authorization: Bearer [access_token_here]'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

``

###### Dart

``

var headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer [access_token_here]'

};
var request = http.Request('GET', Uri.parse('https://api.sourcecodegh.com/v1/gps?Action=GetGPSName&Lati=5.8142835999999996&Longi=0.0746767'));

request.headers.addAll(headers);

http.StreamedResponse response = await request.send();

if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
}
else {
  print(response.reasonPhrase);
}

``

###### Python(http.cient)

``

import http.client

conn = http.client.HTTPSConnection("161.35.163.133")
payload = ''
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer [access_token_here]'
}
conn.request("GET", "/gps?Action=GetGPSName&Lati=5.8142835999999996&Longi=0.0746767", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))

``

## JSON RESPONNSE

``

{
    "GPSName": "GN09206217",
    "Region": "Greater Accra",
    "District": "Ningo Prampram",
    "PostCode": "GN0920",
    "NLat": 5.8143269905622,
    "SLat": 5.81428204422724,
    "WLong": 0.074650000108659,
    "Elong": 0.074694915872864,
    "Area": "BUERKO",
    "Street": ".[Unknown Street]",
    "PlaceName": ""
}

``
If the request is successful, the requested location info is returned as response.


```
