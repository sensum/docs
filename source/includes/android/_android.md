# SensumSDK - Android

## Android Device Compatibility

The Android version of **SensumSDK** can be installed on devices with **5.1.1 (Lollipop)** up to **7.0 (Nougat)**.

We recommend the **Samsung S6**, **S7**, **S8**, **OnePlus X and above** or the **Google Pixel** as suitable devices

## Bluetooth Device Compatibility

* The Android **SensumSDK** supports connecting to BLE devices for reading heart rate measurements. For a list of tested compatible devices please view the <a href = "http://help.sensum.co/knowledge_base/topics/what-type-of-sensors-can-i-use"> list of compatible devices</a> at our Knowledge Centre.

**Note:** This document is regularly updated with new devices. Please contact us for integration details. GSR data is only accessible from Shimmer devices at present.

## Accepted Biometric Data Inputs

The Android **SensumSDK** can accept the following <a href = "#available-metrics">metrics</a>:

  * Heart Rate
  * GSR
  * GPS latitude
  * GPS longitude
  * GPS altitude
  * GPS accuracy
  * GPS speed
  * acceleration
  * acceleration X
  * acceleration Y
  * acceleration Z


## Service Constants

These constants can used to construct message bundled that are then relayed to the Emotion AI service to send and retrieve data.

One example of a call to the service would be to send credentials in order to authorize a user. See <a href = "#submit-credentials-to-service-for-authorization">"Submit Credentials to service for authorization"</a> for an example in how these bundles are constructed.

### API Base URL
`public static final String API_BASEURL = "api-baseurl"`

This is used to pass the base url for API to the **SensumSDK** service which is used for setting up communication with the API

### API Key
`public static final String API_KEY = "api-key"`

This is used to pass the API key to the **SensumSDK** service which is used for setting up communication with the API

### Google Id Token
`public static final String GOOGLE_ID_TOKEN = "google-id-token"`

This is used to pass the Google id token to the **SensumSDK** service which is used for setting up communication with the API

### Google Web Client Id
`public static final String GOOGLE_WEB_CLIENT_ID = "google-web-client-id"`

This is used to pass the API key to the **SensumSDK** service which is used for setting up communication with the API

### Google Login
`public static final int GOOGLE_LOGIN = 126`

This is used to pass a google login message to the **SensumSDK** service

### User Pool Id
`public static final String USER_POOL_ID = "user-poolid"`

This is used to pass the AWS user pool id to the **SensumSDK** service which is used for user authentication

### Identity Pool Id
`public static final String IDENTITY_POOL_ID = "identity-poolid"`

This is used to pass the AWS identity pool id to the **SensumSDK** service which is used for user authentication

### Client Id
`public static final String CLIENT_ID = "client-id"`

This is used to pass a login message (AWS Cognito) to the **SensumSDK** service

### Login
`public static final int LOGIN = 105`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the user login (AWS Cognito)

### Login Filter
`public static final String LOGIN_FILTER = "login-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the user login (AWS Cognito)

### Username
`public static final String USER_NAME = "user-name"`

This is used to pass the username (AWS Cognito) for authentication to the **SensumSDK** service, only authenticated users are able to use the **SensumSDK** service

### Password
`public static final String PASSWORD = "password"`

This is used to pass the password (AWS Cognito) for authentication to the **SensumSDK** service

### BLE Device Filter
`public static final String DEVICE_FILTER = "ble-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the connected ble device

### Heart Rate Filter
`public static final String HR_FILTER = "hr-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate value

### Heart Rate Event Filter
`public static final String HR_EVENT_FILTER = "hr-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate events from the API

### Heart Rate Arousal Filter
`public static final String AROUSAL_FILTER = "arousal-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate arousal from the API

### Wear_HR_Value
`public static final String WEAR_HR_VALUE = "wear-hr-value"`

This is used to pass the Heart Rate value captured using Android Wear to the **SensumSDK** service

### GPS Filter
`public static final String GPS_FILTER = "gps-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the gps values

### Speed Value
`public static final String SPEED_VALUE = "speed-value"`

This is used to pass the captured gps speed value

### Latitude Value
`public static final String LATITUDE_VALUE = "latitude-value"`

This is used to pass the captured gps latitude value

### Longitude Value
`public static final String LONGITUDE_VALUE = "longtitude-value"`

This is used to pass the captured gps longitude value

### Altitude Value
`public static final String ALTITUDE_VALUE = "altitude-value"`

This is used to pass the captured gps altitude value

### Bearing Value
`public static final String BEARING_VALUE = "bearing-value"`

This is used to pass the captured gps bearing value

### Accuracy Value
`public static final String ACCURACY_VALUE = "accuracy-value"`

This is used to pass the captured gps accuracy value

### GPS Event Filter
`public static final String GPS_EVENT_FILTER = "gps-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the gps events from the API

### Accelerometer Filter
`public static final String ACC_FILTER = "acc-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the accelerometer values

### X Value
`public static final String X_VALUE = "x-value"`

This is used to pass the captured accelerometer x value

### Y Value
`public static final String Y_VALUE = "y-value"`

This is used to pass the captured accelerometer y value

### Z Value
`public static final String Z_VALUE = "z-value"`

This is used to pass the captured accelerometer z value

### Accelerometer Event Filter
`public static final String ACC_EVENT_FILTER = "acc-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the accelerometer events from the API

## Accelerometer Registration
`public static final String ACC_FAILED_REGISTERED = "accelerometer-registration"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for checking accelerometer registration

### GSR Filter
`public static final String GSR_FILTER = "gsr-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the gsr values

### GSR Event Filter
`public static final String GSR_EVENT_FILTER = "gsr-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the gsr events from the API

### Input Text
`public static final int INPUT_TEXT = 106`

This is used to filter/pass text & emoji message to the **SensumSDK** service

### Text Message
`public static final String TEXT_MESSAGE = "text-message"`

This is used to pass Text/Emoji value to the **SensumSDK** service

### Extra Data
`public static final String EXTRA_DATA = "extra-data"`

This is used to bundle up extra data to the intents

### Device Name
`public static final String DEVICE_NAME = "device-name"`

This is used to get the connected device name

### Device Address
`public static final String DEVICE_ADDRESS = "device-address"`

This is used to get the connected device address

### Acceleration Capture
`public static final String ACCELERATION_CAPTURE = "acceleration-capture"`

This is used to enable/disable capturing of accelerometer data which is sent to the API

### GPS Capture
`public static final String GPS_CAPTURE = "gps-capture"`

This is used to enable/disable capturing of gps data which is sent to the API

### HR Capture
`public static final String HR_CAPTURE = "heartrate-capture"`

This is used to enable/disable capturing of heart rate data which is sent to the API

### Input Capture
`public static final String INPUT_CAPTURE = "input-capture"`

This is used to enable/disable capturing of text/emoji data which is sent to the API

### GSR Capture
`public static final String GSR_CAPTURE = "gsr-capture"`

This is used to enable/disable capturing of gsr data which is sent to the API

### Device Disconnected
`public static final String DEVICE_DISCONNECTED = "com.example.bluetooth.le.ACTION_GATT_DISCONNECTED"`

This is used to pass a message from the **SensumSDK** service in case of any device disconnection

### Data Rate Send
`public static final String DATA_RATE_SEND = "send-rate"`

This is used to pass the interval rate (in milliseconds) for the data to be sent to the API

### API Response
`public static final String API_RESPONSE = "api-response"`

This is used to pass message from the **SensumSDK** service for the API response

### Toast Message
`public static final String TOAST_MESSAGE = "toast-message"`

This is used to pass informative toast message from the **SensumSDK** service

### Generate Number Of Test Data Records
`public static final String GENERATE_NUMBER_OF_RECORDS = "generate_number_of_records"`

This is used to pass a message to the **SensumSDK** service to get the desired number of test data records from the API

### Generate Test Data
`public static final int GENERATE_TEST_DATA = 129`

This is used to pass a message to the **SensumSDK** service to get test data from the API

### Heart Rate Test Data
`public static final String HR_TEST_DATA_FILTER = "hr-test-data-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate test data from the API

### Input Sentiment Text
`public static final int INPUT_SENTIMENT_TEXT = 128`

This is used to filter/pass text & emoji message for sentiment analysis to the **SensumSDK** service

### Emoji Sentiment Filter
`public static final String EMOJI_SENTIMENT_FILTER = "emoji-sentiment-filter"`

This is used to pass Emoji value to the **SensumSDK** service which is passed to the API for Sentiment analysis

### Text Sentiment Filter 
`public static final String TEXT_SENTIMENT_FILTER = "text-sentiment-filter"`

This is used to pass Text value to the **SensumSDK** service which is passed to the API for Sentiment analysis

### Emotionality
`public static final String EMOTIONALITY = "emotionality"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Emotionality value (Sentiment Analysis) from the API

### Positivity
`public static final String POSITIVITY = "positivity"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Positivity value (Sentiment Analysis) from the API

### Negativity 
`public static final String NEGATIVITY = "negativity"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Negativity value (Sentiment Analysis) from the API

### Connect
`public static final int CONNECT = 101`

This is used to connect to the selected device from the list of the devices

### Connection 
`public static final String CONNECTION = "connection"`

This is used to pass a connection message from the **SensumSDK** service to the front end

### Connection Filter
`public static final String CONNECTION_FILTER = "connection-filter"`

This is used to pass a connection message from the **SensumSDK** service which is used as an intent filter at the front end

### BLE Scan
`public static final int BLE_SCAN = 102`

This is used to pass a ble scan message to the **SensumSDK** service

### Bluetooth Scan
`public static final int BLE_SCAN = 107`

This is used to pass a bluetooth scan message to the **SensumSDK** service

### Bluetooth Connection Filter
`public static final String BLUETOOTH_CONNECTION_FILTER = "bluetooth-connection-filter"`

This is used to filter for bluetooth connection at the front end

### Bluetooth Device Filter
`public static final String BLUETOOTH_DEVICE_FILTER = "bluetooth-device-filter"`

This is used to filter for bluetooth device at the front end

### Connect Bluetooth Device
`public static final int CONNECT_BLUETOOTH_DEVICE = 108`

This is used to pass a connect bluetooth device message to the **SensumSDK** service

### Cancel Capture
`public static final int CANCEL_CAPTURE = 112`

This is used to cancel sending of the captured data to the API

### Start Capture
`public static final int START_CAPTURE = 113`

This is used to start sending of the captured data to the API

### Hello 
`public static final int HELLO = 127`

This is used for the initial communication between developer and frontend to demo how it works

### Hello Filter 
`public static final String HELLO_FILTER = "hello-filter"`

This is used to filter for hello at the front end



## Example Methods

Examples available in the 'Android' tab.

### Initiate connection to service

```java
    private final ServiceConnection mConnection = new ServiceConnection() {
        @Override
        public void onServiceConnected(ComponentName name, IBinder binder) {
            mIsBound = true;
            mServiceMessenger = new Messenger(binder);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {

        }
    };
```

`private final ServiceConnection mConnection = new ServiceConnection()`

Connection made to the service. 

Once bound to the service, the binder object is passed through to messenger to set it up.

&nbsp;

&nbsp;

&nbsp;

&nbsp;



### Submit Credentials to service for authorization (Cognito User Pools)

```java
    void submit() {
        Bundle bundle = new Bundle();
        bundle.putString(USER_NAME, "username");
        bundle.putString(PASSWORD, "password");
        bundle.putString(USER_POOL_ID, "userPoolId");
        bundle.putString(CLIENT_ID, "clientId");
        bundle.putString(API_BASEURL, "apiBaseUrl");
        bundle.putString(API_KEY, "apiKey");
        sendToService(bundle, LOGIN);
    }
```

`void submit()`

Sets up the credential bundle to be sent to the **SensumSDK** service this needs to be sent first to the **SensumSDK** service as only authenticated users can use the service.

&nbsp;

&nbsp;

&nbsp;

&nbsp;

### Submit Credentials to service for authorization (Google Sign-In)

```java
    void submit() {
        Bundle bundle = new Bundle();
        bundle.putString(API_BASEURL, apiBaseUrl);
        bundle.putString(API_KEY, apiKey);
        bundle.putString(IDENTITY_POOL_ID, identityPoolId);
        bundle.putString(GOOGLE_ID_TOKEN, googleIdToken);
        bundle.putString(GOOGLE_WEB_CLIENT_ID, googleWebClientId);
        sendToService(bundle, GOOGLE_LOGIN);
    }
```
Follow Google's <a href = "https://developers.google.com/identity/sign-in/android/start-integrating">instructions</a> to add Google Sign-In to your application.

Once successfully implemented you must send the Google Id token for the Google Sign-In application to us.

`void submit()`

Sets up the credential bundle to be sent to the **SensumSDK** service this needs to be sent first to the **SensumSDK** service as only authenticated users can use the service.


&nbsp;

&nbsp;

&nbsp;

&nbsp;


### Send a data message to the service

```java
    public void sendToService(Bundle bundle, int argValue) {
        Message message = Message.obtain();
        message.arg1 = argValue;
        message.setData(bundle);
        try {
            mServiceMessenger.send(message);
            Toast.makeText(this, "Requested the service", Toast.LENGTH_SHORT).show();
        } catch (RemoteException e) {
            e.printStackTrace();
        }
    }
```

`public void sendToService(Bundle bundle, int argValue)`

Send message to the service.

 * **Parameters:**
   * `bundle` — any data that needs passed to the service
   * `argValue` — for service handler to switch on


&nbsp;

&nbsp;

&nbsp;

&nbsp;



### Create New Broadcast Receiver Object

```java
    private BroadcastReceiver mMessageReceiver = new BroadcastReceiver() {
        @Override
        public void onReceive(Context context, Intent intent) {
            String action = intent.getAction();

            switch (action) {
                case HELLO_FILTER:
                    Toast.makeText(MainActivity.this, intent.getStringExtra(EXTRA_DATA), Toast.LENGTH_LONG).show();
                    break;
                case GPS_FILTER:
                    Bundle gpsBundle = intent.getBundleExtra(EXTRA_DATA);
                    break;
                case ACC_FILTER:
                    Bundle accBundle = intent.getBundleExtra(EXTRA_DATA);
                    isAcc = true;
                    break;
                case HR_FILTER:
                    String hrValue = intent.getStringExtra(EXTRA_DATA);
                    break;
                case GSR_FILTER:
                    String gsrValue = intent.getStringExtra(EXTRA_DATA);
                    break;
                case API_RESPONSE:
                    String apiResponse = intent.getStringExtra(EXTRA_DATA);
                    break;
                case TOAST_MESSAGE:
                    String toastMessage = intent.getStringExtra(EXTRA_DATA);
                    break;
               case HR_EVENT_FILTER:
                   Break;
               case AROUSAL_FILTER:
                   break;
               case GSR_EVENT_FILTER:
                   break;
               case EMOJI_SENTIMENT_FILTER:
                   Bundle emojiSentimentBundle = intent.getBundleExtra(EXTRA_DATA);
                   break;
               case TEXT_SENTIMENT_FILTER:
                   Bundle textSentimentBundle = intent.getBundleExtra(EXTRA_DATA);
                   break;
               case HR_TEST_DATA_FILTER:
                   break;
            }

        }
    };
```

`private BroadcastReceiver mMessageReceiver = new BroadcastReceiver()`

Broadcast receiver with the list of registered filters.



&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

### Update IntentFilter with new Actions

```java
    private IntentFilter updateIntentFilter() {
        final IntentFilter intentFilter = new IntentFilter();

        intentFilter.addAction(HELLO_FILTER);
        intentFilter.addAction(GPS_FILTER);
        intentFilter.addAction(ACC_FILTER);
        intentFilter.addAction(HR_FILTER);
        intentFilter.addAction(GSR_FILTER);
        intentFilter.addAction(API_RESPONSE);
        intentFilter.addAction(TOAST_MESSAGE);
        intentFilter.addAction(HR_EVENT_FILTER);
        intentFilter.addAction(AROUSAL_FILTER);
        intentFilter.addAction(GSR_EVENT_FILTER);
        intentFilter.addAction(EMOJI_SENTIMENT_FILTER);
        intentFilter.addAction(TEXT_SENTIMENT_FILTER);
        intentFilter.addAction(HR_TEST_DATA_FILTER);
        return intentFilter;
    }
```


`private IntentFilter updateIntentFilter()`

 * **Returns:** an intent filter with a list of actions.
&nbsp;

&nbsp;

&nbsp;

&nbsp;


&nbsp;

&nbsp;

&nbsp;

&nbsp;


&nbsp;


### Start Biometric Data Capture

```java
    private void startCaptureSetUp() {
        Toast.makeText(this, "Started capturing", Toast.LENGTH_SHORT).show();
        Log.d(TAG, "Started capturing");
        sendToService(getCaptureBundle(), START_CAPTURE);
    }
```
`private void startCaptureSetUp()`

Starts capturing of biometric/contextual data.
&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;


&nbsp;



### Get Capture Bundle

```java
    private Bundle getCaptureBundle() {
        Bundle bundle = new Bundle();
        bundle.putBoolean(ACCELERATION_CAPTURE, true);
        bundle.putBoolean(HR_CAPTURE, true); 
        bundle.putBoolean(GPS_CAPTURE, true); 
        bundle.putBoolean(GSR_CAPTURE, true); 
        bundle.putBoolean(INPUT_CAPTURE, true);
        bundle.putLong(DATA_RATE_SEND, 20 * 1000);
        return bundle;
    }
```


`private Bundle getCaptureBundle()`

Sets up the bundle data for capture using the service constants.

 * **Returns:** capture bundle

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;



### Stop Biometric Data Capture

```java
    private void stopCaptureSetUp() {
        Toast.makeText(this, "Stopped capturing", Toast.LENGTH_SHORT).show();
        sendToService(getCaptureBundle(), ServiceConstants.CANCEL_CAPTURE);
    }
```
`private void stopCaptureSetUp()`

Stops capturing of biometric/contextual data.


&nbsp;

&nbsp;

&nbsp;

&nbsp;



