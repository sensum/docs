# SensumSDK - Android

## Android Device Compatibility

The Android version of **SensumSDK** can be installed on devices with **6.0 (Marshmallow)** up to **8.0 (Oreo)**.

We recommend the **Samsung S6**, **S7**, **S8**, **OnePlus X and above** or the **Google Pixel** as suitable devices

## Bluetooth Device Compatibility

* The Android **SensumSDK** supports connecting to BLE and Bluetooth devices for reading heart rate measurements. For a list of tested compatible devices please view the <a href = "http://help.sensum.co/knowledge_base/topics/what-type-of-sensors-can-i-use"> list of compatible devices</a> at our Knowledge Centre.  // TODO FIX THIS LINK

**Note:** This document is regularly updated with new devices. Please contact us for integration details. GSR data is only accessible from Shimmer devices at present.

## Accepted Biometric Data Inputs

The Android **SensumSDK** can accept the following <a href = "#available-metrics">metrics</a>:

  * Heart Rate
  * GSR
  * Location Latitude
  * Location Longitude
  * Location Altitude
  * Location Accuracy
  * Location Speed
  * Acceleration
  * Acceleration X
  * Acceleration Y
  * Acceleration Z


## Service Constants

These constants can be used to construct message bundles that are then relayed to the Emotion AI service to send and retrieve data.

One example of a call to the service would be to send credentials in order to authenticate a user. See <a href = "#submit-credentials-to-service-for-authorization">"Submit Credentials to service for authorization"</a> for an example in how these bundles are constructed.

### API Base URL
`public static final String API_BASEURL = "api-baseurl"`

This is used to pass the base url for API to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

### API Key
`public static final String API_KEY = "api-key"`

This is used to pass the API key to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

### Google Id Token
`public static final String GOOGLE_ID_TOKEN = "google-id-token"`

This is used to pass the Google id token to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

### Google Web Client Id
`public static final String GOOGLE_WEB_CLIENT_ID = "google-web-client-id"`

This is used to pass the Google web client id to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

### Google Login
`public static final int GOOGLE_LOGIN = 126`

This is used to pass a google login message to the **SensumSDK** service

### Login Filter
`public static final String LOGIN_FILTER = "login-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the user login

### Identity Pool Id
`public static final String IDENTITY_POOL_ID = "identity-poolid"`

This is used to pass the AWS identity pool id to the **SensumSDK** service which is used for user authentication

### Heart Rate Filter
`public static final String HR_FILTER = "hr-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate value

### Heart Rate Event Filter
`public static final String HR_EVENT_FILTER = "hr-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate events from the **SensumAPI**

### Heart Rate Arousal Filter
`public static final String AROUSAL_FILTER = "arousal-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate arousal from the **SensumAPI**

### GPS Filter
`public static final String GPS_FILTER = "gps-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GPS values

### Speed Value
`public static final String SPEED_VALUE = "speed-value"`

This is used to pass the captured GPS speed value

### Latitude Value
`public static final String LATITUDE_VALUE = "latitude-value"`

This is used to pass the captured GPS latitude value

### Longitude Value
`public static final String LONGITUDE_VALUE = "longtitude-value"`

This is used to pass the captured GPS longitude value

### Altitude Value
`public static final String ALTITUDE_VALUE = "altitude-value"`

This is used to pass the captured GPS altitude value

### Bearing Value
`public static final String BEARING_VALUE = "bearing-value"`

This is used to pass the captured GPS bearing value

### Accuracy Value
`public static final String ACCURACY_VALUE = "accuracy-value"`

This is used to pass the captured GPS accuracy value

### GPS Event Filter
`public static final String GPS_EVENT_FILTER = "gps-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GPS events from the **SensumAPI**

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

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the accelerometer events from the **SensumAPI**

### Accelerometer Registration
`public static final String ACC_FAILED_REGISTERED = "accelerometer-registration"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for checking accelerometer registration

### GSR Filter
`public static final String GSR_FILTER = "gsr-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GSR values

### GSR Event Filter
`public static final String GSR_EVENT_FILTER = "gsr-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GSR events from the **SensumAPI**

### Extra Data
`public static final String EXTRA_DATA = "extra-data"`

This is used to bundle up extra data to the intents

### Acceleration Capture
`public static final String ACCELERATION_CAPTURE = "acceleration-capture"`

This is used to enable/disable capturing of accelerometer data which is sent to the **SensumAPI**

### GPS Capture
`public static final String GPS_CAPTURE = "gps-capture"`

This is used to enable/disable capturing of GPS data which is sent to the **SensumAPI**

### HR Capture
`public static final String HR_CAPTURE = "heartrate-capture"`

This is used to enable/disable capturing of heart rate data which is sent to the **SensumAPI**

### Input Capture
`public static final String INPUT_CAPTURE = "input-capture"`

This is used to enable/disable capturing of text/emoji data which is sent to the **SensumAPI**

### GSR Capture
`public static final String GSR_CAPTURE = "gsr-capture"`

This is used to enable/disable capturing of GSR data which is sent to the **SensumAPI**

### Data Rate Send
`public static final String DATA_RATE_SEND = "send-rate"`

This is used to pass the interval rate (in milliseconds) for the data to be sent to the **SensumAPI**

### API Response
`public static final String API_RESPONSE = "api-response"`

This is used to pass message from the **SensumSDK** service for the **SensumAPI** response

### Toast Message
`public static final String TOAST_MESSAGE = "toast-message"`

This is used to pass informative toast message from the **SensumSDK** service

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

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Emotionality value (Sentiment Analysis) from the **SensumAPI**

### Positivity
`public static final String POSITIVITY = "positivity"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Positivity value (Sentiment Analysis) from the **SensumAPI**

### Negativity 
`public static final String NEGATIVITY = "negativity"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Negativity value (Sentiment Analysis) from the **SensumAPI**

### Cancel Capture
`public static final int CANCEL_CAPTURE = 112`

This is used to cancel sending of the captured data to the **SensumAPI**

### Start Capture
`public static final int START_CAPTURE = 113`

This is used to start sending of the captured data to the **SensumAPI**

### Hello 
`public static final int HELLO = 127`

This is used for the initial communication between developer and frontend to demo how it works

### Hello Filter 
`public static final String HELLO_FILTER = "hello-filter"`

This is used to filter for hello at the front end

### Device Name
`public static final String DEVICE_NAME = "device-name"`

This is used to get the connected device name

### Device Address
`public static final String DEVICE_ADDRESS = "device-address"`

This is used to get the connected device address

### Connection 
`public static final String CONNECTION = "connection"`

This is used to pass a connection message from the **SensumSDK** service to the front end

### BLE Scan
`public static final int BLE_SCAN = 102`

This is used to pass a BLE scan message to the **SensumSDK** service

### Connect BLE Device
`public static final int CONNECT_BLE = 101`

This is used to pass a connect BLE device message to the **SensumSDK** service

### BLE Connection Filter
`public static final String BLE_CONNECTION_FILTER = "ble-connected-filter"`

This is used to pass a BLE connection message from the **SensumSDK** service which is used as an intent filter at the front end

### BLE Device Filter
`public static final String BLE_DEVICE_FILTER = "ble-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the connected ble device

### BLE Device Name
`public static final String BLE_DEVICE_NAME = "ble-device-name"`

This is used to pass the BLE device name from the **SensumSDK** service

### Disconnect BLE Device
`public static final int DISCONNECT_BLE = 134`

This is used to disconnect a BLE device

### BLE Connectivity
`public static final String BLE_CONNECTIVITY = "ble-connectivity"`

This is used to pass a BLE connectivity message from the **SensumSDK** service to the front end

### Connected Devices
`public static final int CONNECTED_DEVICES = 136`

This is used to pass a message to the **SensumSDK** to get the connected device names

### Connected Devices Filter
`public static final String CONNECTED_DEVICES_FILTER = "connected-devices-filter"`

This is used to filter for the connected devices

### Bluetooth Device Name
`public static final String BLUETOOTH_DEVICE_NAME = "bluetooth-device-name"`

This is used to pass the bluetooth device name from the **SensumSDK** service

### Bluetooth Scan
`public static final int BLUETOOTH_SCAN = 107`

This is used to pass a bluetooth scan message to the **SensumSDK** service

### Disconnect Bluetooth Device
`public static final int DISCONNECT_BLUETOOTH = 135`

This is used to disconnect a bluetooth device

### Connect Bluetooth Device
`public static final int CONNECT_BLUETOOTH_DEVICE = 108`

This is used to pass a connect bluetooth device message to the **SensumSDK** service

### Bluetooth Connectivity
`public static final String BT_CONNECTIVITY = "bt-connectivity"`

This is used to pass a bluetooth connectivity message from the **SensumSDK** service to the front end

### Bluetooth Connection Filter
`public static final String BLUETOOTH_CONNECTION_FILTER = "bluetooth-connected-filter"`

This is used to filter for bluetooth connection at the front end

### Bluetooth Device Filter
`public static final String BLUETOOTH_DEVICE_FILTER = "bluetooth-device-filter"`

This is used to filter for bluetooth device at the front end

### Device Disconnected
`public static final String DEVICE_DISCONNECTED = "com.example.bluetooth.le.ACTION_GATT_DISCONNECTED"`

This is used to pass a message from the **SensumSDK** service in case of any device disconnection

### Realm Response
`public static final String REALM_RESPONSE = "realm-response"`

This is used to pass message from the **SensumSDK** service for data manipulation in realm for a session



## Example Methods

Examples available in the 'Android' tab.

### Initiate connection to service

```java
    private final ServiceConnection mConnection = new ServiceConnection() {
        @Override
        public void onServiceConnected(ComponentName componentName, IBinder iBinder) {
            SdkService.LocalBinder binder = (SdkService.LocalBinder) iBinder;
            mService = binder.getService();
            mServiceMessenger = mService.mServiceMessenger;
        }

        @Override
        public void onServiceDisconnected(ComponentName componentName) {

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

Once successfully implemented you must send the Google Id token for the Google Sign-In application to us to authenticate access. You can contact // TODO INSERT CONTACT DETAILS FOR ADDING GOOGLE ID TO AWS IAM

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
               case CONNECTED_DEVICES_FILTER:
                    String bleDeviceName = intent.getStringExtra(ServiceConstants.BLE_DEVICE_NAME);
                    String btDeviceName = intent.getStringExtra(ServiceConstants.BLUETOOTH_DEVICE_NAME);
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
        intentFilter.addAction(CONNECTED_DEVICES_FILTER);
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
        sendToService(getCaptureBundle(), CANCEL_CAPTURE);
    }
```
`private void stopCaptureSetUp()`

Stops capturing of biometric/contextual data.


&nbsp;

&nbsp;

&nbsp;

&nbsp;



