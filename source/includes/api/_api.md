

# SensumAPI

## Introduction
> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

**SensumAPI** enables you to access our Empathic AI Platform, which processes data (eg. from sensors) into human-state values.  Our API is designed to be RESTful, responding to HTTP requests with bodies in JSON format. All requests require that the `Content-Type: application/json` header be specified.
**SensumAPI** is also cross-origin resource sharing ready.

**SensumSDK** handles many of these requests and responses natively. It can however be useful to use the **SensumAPI** directly.



## URI Structure

**SensumAPI** uses URI resources to provide access to its services. To use a RESTful API, your application will use HTTP Methods(GET, POST, etc.) to request and parse a response. **SensumAPI** uses JSON for communication between your application and the server.

An example URI:
<a href="">https://api.sensum.co/v0/testdata</a>

## Authorization

**SensumAPI** uses a combination of an API Key and request signing to authorize access. You can register a new API Key by contacting us.

**SensumAPI** expects each call to contain the following headers to gain access:

 * Content-Type: `application/json`
 * Authorization: `$AWSv4Signature`
 * X-API-Key: `$YourAPIKey`(For trial usage use "PublicDemoKeyForDocumentation")

To calculate the value for the Authorization header you must calculate a hash of your request, add extra information, then add the AWS secret key in order to create a signing key and then use this to sign the request.
To learn more about generating the Signature please read the <a href="https://docs.aws.amazon.com/general/latest/gr/signature-v4-examples.html">AWS Documentation on Signature v4</a>

When using the SDK, the signature will be automatically generated when making API calls through it.

<aside class="notice">Replace the above authorization header with the AWS Signature generated after login and X-API-Key with your personal API key.</aside>

## Available Metrics

Below are the metrics that **SensumAPI** can analyse and the units that the data is posted in

|Metric Name|Unit|
|-----------|----|
|<a href = "http://help.sensum.co/knowledge_base/topics/why-measure-heart-rate">`heartrate`</a>|bpm|
|`breathingrate`|bpm|
|`temperature`|<sup>o</sup>C, assumed to be ambient/external|
|`skintemperature`|<sup>o</sup>C|
|<a href = "http://help.sensum.co/knowledge_base/topics/what-is-gsr">`gsr`</a>| microsiemens<sup>*</sup>|
|`location_latitude`|deg|
|`location_longitude`|deg|
|`location_altitude`|m|
|`location_accuracy`|or location_accuracy_horizontal/vertical if available|
|`location_speed`|m/s|
|`acceleration`|linear acceleration in m/s<sup>2**</sup>|
|`acceleration_x`|m/s<sup>2</sup>|
|`acceleration_y`|m/s<sup>2</sup>|
|`acceleration_z`|m/s<sup>2</sup>|

<sup>*</sup> The GSR (galvanic skin response) unit of skin conductance 'microsiemens' is the inverse of the skin resistance; some devices return GSR as resistance in Ohms and this must be converted before upload, i.e. if a device returns values in x kOhms, the conversion is 1/(1000*x)

<sup>**</sup> All acceleration values should exclude gravity and be in m/s<sup>2</sup>

## SensumAPI Analysis Responses

| Input Metric(s)        | Generated Events       | Generated Records | Generated Stats                                    |
|------------------------|------------------------|-------------------|----------------------------------------------------|
| *any*                  | <a href = "#events">Events for that Metric</a> |                   | [Stats for that event](#stats)                     |
| `heartrate`            |                        | `arousal`         | `arousal` [(See Fuzzy Class Stats)](#fuzzy-class-stats)  |
| `gsr`                  |                        | `engagement`      | `engagement` [(See Fuzzy Class Stats)](#fuzzy-class-stats) |
| `acceleration_[x,y,z]` |                        | `activity`        | `activity` [(See Fuzzy Class Stats)](#fuzzy-class-stats) |

### Events
|  Event Fields | Type                                                         	| Meaning                                                                                                                         	|
|--------------	|--------------------------------------------------------------	|---------------------------------------------------------------------------------------------------------------------------------	|
| `time`         	| UTC Timestamp (ms)                                           	| Time of event                                                                                                                   	|
| `value`        	| String: One of ['normal', 'rising', 'falling', 'max', 'min'] 	| Type of event (normal is not currently used)                                                                                    	|
| `severity` &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;    	| Float                                                        	| Relative severity of the event, i.e. how much of value change between forward/backward events with respect to the average value 	|

### Stats

| Stats Field | Type            | Meaning                                                                            |
|-------------|-----------------|------------------------------------------------------------------------------------|
| `avg`         | Float           | average (mean) value                                                               |
| `duration`    | Float (seconds) | time between first and last analysed records                                       |
| `max`         | Float           | max value                                                                          |
| `min`         | Float           | min value                                                                          |
| `std`         | Float           | standard deviation of the record                                                   |
| `percentiles` | Object(dict)    | 10th, 50th, and 90th <a href = "https://en.wikipedia.org/wiki/Percentile"> percentile values </a>|

### Fuzzy Class Stats

For <a href = "https://en.wikipedia.org/wiki/Fuzzy_classification">"fuzzy"</a> classification outputs such as `arousal`, `engagement` and `activity`, an additional stats structure is used containing 3 fields:

| Field | Type | Meaning |
|-------|------|---------|
| `value` | Float| [0-1] activation value |
| `dominant` | string | label of the dominant classification category |
| `sectors` | Object(dict) | per-category-label activivation i.e `{label:value,...}`

Current Sector Labels (highest to lowest activation value):

* Activity : `active`, `inactive`
* Arousal : `excited`, `activated`, `calm`, `passive`, `relaxed`
* Engagement: `highly engaged`, `engaged`, `activated`, `neutral`


## Send text data to analyse emoji and text sentiment  

This endpoint allows users to send strings of text to our service for emotional sentiment analysis.

The service will return a JSON object that contains Positivity, Negativity and Emotionality values for emojis and text.



### HTTP Request

`POST https://api.sensum.co/v0/sentiment`

<aside class="warning">
To perform this operation, you must be authenticated by means of the following headers:
API Key, Authorization.
</aside>

###Glossary

|Term|Description|
|----|-----------|
|`positivity`| The level of positive emotion expressed in an input(Scale: 0 to +1)|
|`negativity`| The level of negative emotion expressed in an input(Scale: 0 to +1)|
|`emotionality`| The overall strength of emotion contained in an input(Scale: -1 to +1)*|

* Values greater than 0 imply positive feelings, values less than 0 imply negative feelings, while 0 implies no emotional response.


> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Authorization' : 'AWS Sig v4 Key',
  'x-api-key' : 'PublicDemoKeyForDocumentation'

};

var data = {
  "text":"👌👌👌"
};

$.ajax({
  url: 'https://api.sensum.co/v0/sentiment',
  method: 'post',
  data: JSON.stringify(data);
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Content-Type':'application/json',
  'Authorization' : 'AWS Sig v4 Key',
  'x-api-key' : 'PublicDemoKeyForDocumentation'

};

var data = {
  "text":"👌👌👌"
};


fetch('https://api.sensum.co/v0/sentiment',
{
  method: 'POST',
  body : body,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```


```python
import requests
headers = {
  'Content-Type':'application/json',
  'Authorization' : 'AWS Sig v4 Key',
  'x-api-key' : 'PublicDemoKeyForDocumentation'
}


data = {
  "text":"👌👌👌"
}

r = requests.post('https://api.sensum.co/v0/sentiment', data=data, headers = headers)

print r.json()
```


### Responses

Status|Meaning|Description
---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response

### Examples

Please refer to the code samples for request and response examples

> Text Only - Unemotional

> Request

```json
{
  "text": "This is nothing"
}
```

> Response

```json
{
  "emoji_sentiment": null,
  "text_sentiment": {
    "emotionality": 0.0, //Aggregate Emotionality Score from -1,+1
    "negativity": 0.0, // Negativity Score from 0 to +1
    "positivity": 0.0  // Positivity Score from 0 to +1
   }
}
```
> Text Only - Emotional

> Request

```json
{
  "text": "This was a very good test"
}
```
> Response

```json
{
  "emoji_sentiment": null,
  "text_sentiment": {
    "positivity": 0.444,
    "negativity": 0.0,
    "emotionality": 0.4927
  }
}
```
> Emoji

> Request

```json
{
  "text":"👌👌👌"
}
```

> Response

```json
{
  "text_sentiment": {
    "negativity": 0.0,
    "positivity": 0.0,
    "emotionality": 0.0
  },
  "emoji_sentiment": {
    "positivity": 0.6575529733,
    "negativity": 0.0936431989,
    "emotionality": 0.4236068641
  }
}
```

## Send data for events analysis

This endpoint allows the user to send data to the Empathic AI service for analysis. The response will return a series of significant events.

An event is triggered when there is a statistically significant timeseries change detected in an incoming data stream, whether that is from a Bluetooth sensor or internal sensor such as Accelerometer. Depending on the data stream applied, this can indicate a shift or change in emotional or activity state.

The severity of an event is dependent on

* How "steep" the event is and
* How "isolated" the event is with respect to any events identified before / after it.   

### HTTP Request

`POST https://api.sensum.co/v0/events`

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Authorization': 'AWS_Sig v4 Key',
  'x-api-key': 'Public'

};

var data = {
    "records": {
      "heartrate": [
        {
          "time": 1502807187332,
          "value": 111.77347523527911
        },
        {
          "time": 1502807188332,
          "value": 112.89604978090439
        },
        {
          "time": 1502807189332,
          "value": 112.37719504311998
        },
        {
          "time": 1502807190332,
          "value": 113.68469103590627
        },
        {
          "time": 1502807191332,
          "value": 113.67799449012763
        },
        {
          "time": 1502807192332,
          "value": 112.71988545819869
        },
        {
          "time": 1502807193332,
          "value": 113.05775062793727
        },
        {
          "time": 1502807194332,
          "value": 114.53499763344529
        },
        {
          "time": 1502807195332,
          "value": 115.4964191594706
        },
        {
          "time": 1502807196332,
          "value": 115.31744641217797
        }
      ]
    }
  };

$.ajax({
  url: 'https://api.sensum.co/v0/events',
  method: 'post',
  data: JSON.stringify(data),
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
    "records": {
      "heartrate": [
        {
          "time": 1502807187332,
          "value": 111.77347523527911
        },
        {
          "time": 1502807188332,
          "value": 112.89604978090439
        },
        {
          "time": 1502807189332,
          "value": 112.37719504311998
        },
        {
          "time": 1502807190332,
          "value": 113.68469103590627
        },
        {
          "time": 1502807191332,
          "value": 113.67799449012763
        },
        {
          "time": 1502807192332,
          "value": 112.71988545819869
        },
        {
          "time": 1502807193332,
          "value": 113.05775062793727
        },
        {
          "time": 1502807194332,
          "value": 114.53499763344529
        },
        {
          "time": 1502807195332,
          "value": 115.4964191594706
        },
        {
          "time": 1502807196332,
          "value": 115.31744641217797
        }
      ]
    }
  }
';
const headers = {
  'Content-Type':'application/json',
  'Authorization' : 'AWS Sig v4 Key',
  'x-api-key' : 'PublicDemoKeyForDocumentation'

};

fetch('https://api.sensum.co/v0/events',
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

```python
import requests
headers = {
  'Content-Type':'application/json',,
  'Authorization' : 'AWS Sig v4 Key',
  'x-api-key' : 'PublicDemoKeyForDocumentation'
}

data = {
    "records": {
      "heartrate": [
        {
          "time": 1502807187332,
          "value": 111.77347523527911
        },
        {
          "time": 1502807188332,
          "value": 112.89604978090439
        },
        {
          "time": 1502807189332,
          "value": 112.37719504311998
        },
        {
          "time": 1502807190332,
          "value": 113.68469103590627
        },
        {
          "time": 1502807191332,
          "value": 113.67799449012763
        },
        {
          "time": 1502807192332,
          "value": 112.71988545819869
        },
        {
          "time": 1502807193332,
          "value": 113.05775062793727
        },
        {
          "time": 1502807194332,
          "value": 114.53499763344529
        },
        {
          "time": 1502807195332,
          "value": 115.4964191594706
        },
        {
          "time": 1502807196332,
          "value": 115.31744641217797
        }
      ]
    }
  }


r = requests.post('https://api.sensum.co/v0/events', params = data, headers = headers)

print r.json()
```

> Body parameter

```json
{
    "records": {
      "heartrate": [
        {
          "time": 1502807187332,
          "value": 111.77347523527911
        },
        {
          "time": 1502807188332,
          "value": 112.89604978090439
        },
        {
          "time": 1502807189332,
          "value": 112.37719504311998
        },
        {
          "time": 1502807190332,
          "value": 113.68469103590627
        },
        {
          "time": 1502807191332,
          "value": 113.67799449012763
        },
        {
          "time": 1502807192332,
          "value": 112.71988545819869
        },
        {
          "time": 1502807193332,
          "value": 113.05775062793727
        },
        {
          "time": 1502807194332,
          "value": 114.53499763344529
        },
        {
          "time": 1502807195332,
          "value": 115.4964191594706
        },
        {
          "time": 1502807196332,
          "value": 115.31744641217797
        }
      ]
    }
  }
```
### Responses

Status|Meaning|Description
---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful request

### Response Headers

Status|Header|Type|Format|Description
---|---|---|---|---|
200|Access-Control-Allow-Origin|string||

> Example responses

```json
{
    "events":{
        "heartrate":[
            {"time":1502807187000,"value":"min","severity":0.03176537181134584},
            {"time":1502807196000,"value":"max","severity":0.03176537181134584}
        ]
    },
    "stats":{
        "heartrate":{
            "avg":113.55359048765672,
            "duration":9,
            "max":115.4964191594706,
            "min":111.77347523527911,
            "std":1.175057115344551,
            "percentiles":{"10":112.3168230623359,"50":113.36787255903245,"90":115.33534368690724}}
    },
    "records":{
        "arousal":[
            {"time":1502807187332,"value":5.359549491038813e-15},
            {"time":1502807188332,"value":0.052921639437207874},
            {"time":1502807189332,"value":0.028461220785887004},
            {"time":1502807190332,"value":0.09010062973692541},
            {"time":1502807191332,"value":0.08978493383721622},
            {"time":1502807192332,"value":0.044616707881203976},
            {"time":1502807193332,"value":0.06054471797280525},
            {"time":1502807194332,"value":0.13018671519236316},
            {"time":1502807195332,"value":0.17551110237516387},
            {"time":1502807196332,"value":0.16707377298958567}
        ]
    },
    "exec_time":0.12196207046508789
}
```
<aside class="warning">
To perform this operation, you must be authenticated by means of the following headers:
X-API-Key, Authorization
</aside>

## Errors

**SensumAPI** uses the following error codes:


Error Code | Meaning|
---------- | -------|
400 | Bad Request - Your Request may have caused an error|
401 | Unauthorized - This error will likely occur if the Cognito Authorization Header (AWS Signature v4) is either missing or invalid.|
403 | Forbidden -This error will likely occur if the API Key Header is either invalid or missing.|
405 | Method Not Allowed - You have attempted to make a request using a HTTP Method that is invalid for the requested resource.|
429 | Too Many Requests - You have made more requests than is allowed under the usage plan.|
500 | Internal Server Error - There is an error with our service
503 | Service Unavailable - Our service is down for maintenance. Please try again later.
