# Android SensumSDK Service Constants

## API Base URL
`public static final String API_BASEURL = "api-baseurl"`

This is used to pass the base url for API to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

## API Key
`public static final String API_KEY = "api-key"`

This is used to pass the API key to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

## Google Id Token
`public static final String GOOGLE_ID_TOKEN = "google-id-token"`

This is used to pass the Google id token to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

## Google Web Client Id
`public static final String GOOGLE_WEB_CLIENT_ID = "google-web-client-id"`

This is used to pass the API key to the **SensumSDK** service which is used for setting up communication with the **SensumAPI**

## Google Login
`public static final int GOOGLE_LOGIN = 126`

This is used to pass a google login message to the **SensumSDK** service

## User Pool Id
`public static final String USER_POOL_ID = "user-poolid"`

This is used to pass the AWS user pool id to the **SensumSDK** service which is used for user authentication

## Identity Pool Id
`public static final String IDENTITY_POOL_ID = "identity-poolid"`

This is used to pass the AWS identity pool id to the **SensumSDK** service which is used for user authentication

## Client Id
`public static final String CLIENT_ID = "client-id"`

This is used to pass a login message (AWS Cognito) to the **SensumSDK** service

## Login
`public static final int LOGIN = 105`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the user login (AWS Cognito)

## Login Filter
`public static final String LOGIN_FILTER = "login-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the user login (AWS Cognito)

## Username
`public static final String USER_NAME = "user-name"`

This is used to pass the username (AWS Cognito) for authentication to the **SensumSDK** service, only authenticated users are able to use the **SensumSDK** service

## Password
`public static final String PASSWORD = "password"`

This is used to pass the password (AWS Cognito) for authentication to the **SensumSDK** service

## BLE Device Filter
`public static final String DEVICE_FILTER = "ble-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for the connected ble device

## Heart Rate Filter
`public static final String HR_FILTER = "hr-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate value

## Heart Rate Event Filter
`public static final String HR_EVENT_FILTER = "hr-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate events from the **SensumAPI**

## Heart Rate Arousal Filter
`public static final String AROUSAL_FILTER = "arousal-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate arousal from the **SensumAPI**

## Wear_HR_Value
`public static final String WEAR_HR_VALUE = "wear-hr-value"`

This is used to pass the Heart Rate value captured using Android Wear to the **SensumSDK** service

## GPS Filter
`public static final String GPS_FILTER = "gps-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GPS values

## Speed Value
`public static final String SPEED_VALUE = "speed-value"`

This is used to pass the captured GPS speed value

## Latitude Value
`public static final String LATITUDE_VALUE = "latitude-value"`

This is used to pass the captured GPS latitude value

## Longitude Value
`public static final String LONGITUDE_VALUE = "longtitude-value"`

This is used to pass the captured GPS longitude value

## Altitude Value
`public static final String ALTITUDE_VALUE = "altitude-value"`

This is used to pass the captured gps altitude value

## Bearing Value
`public static final String BEARING_VALUE = "bearing-value"`

This is used to pass the captured GPS bearing value

## Accuracy Value
`public static final String ACCURACY_VALUE = "accuracy-value"`

This is used to pass the captured GPS accuracy value

## GPS Event Filter
`public static final String GPS_EVENT_FILTER = "gps-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GPS events from the **SensumAPI**

## Accelerometer Filter
`public static final String ACC_FILTER = "acc-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the accelerometer values

## X Value
`public static final String X_VALUE = "x-value"`

This is used to pass the captured accelerometer x value

## Y Value
`public static final String Y_VALUE = "y-value"`

This is used to pass the captured accelerometer y value

## Z Value
`public static final String Z_VALUE = "z-value"`

This is used to pass the captured accelerometer z value

## Accelerometer Event Filter
`public static final String ACC_EVENT_FILTER = "acc-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the accelerometer events from the **SensumAPI**

## Accelerometer Registration
`public static final String ACC_FAILED_REGISTERED = "accelerometer-registration"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for checking accelerometer registration

## GSR Filter
`public static final String GSR_FILTER = "gsr-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GSR values

## GSR Event Filter
`public static final String GSR_EVENT_FILTER = "gsr-event-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the GSR events from the **SensumAPI**

## Input Text
`public static final int INPUT_TEXT = 106`

This is used to filter/pass text & emoji message to the **SensumSDK** service

## Text Message
`public static final String TEXT_MESSAGE = "text-message"`

This is used to pass Text/Emoji value to the **SensumSDK** service

## Extra Data
`public static final String EXTRA_DATA = "extra-data"`

This is used to bundle up extra data to the intents

## Device Name
`public static final String DEVICE_NAME = "device-name"`

This is used to get the connected device name

## Device Address
`public static final String DEVICE_ADDRESS = "device-address"`

This is used to get the connected device address

## Acceleration Capture
`public static final String ACCELERATION_CAPTURE = "acceleration-capture"`

This is used to enable/disable capturing of accelerometer data which is sent to the **SensumAPI**

## GPS Capture
`public static final String GPS_CAPTURE = "gps-capture"`

This is used to enable/disable capturing of GPS data which is sent to the **SensumAPI**

## HR Capture
`public static final String HR_CAPTURE = "heartrate-capture"`

This is used to enable/disable capturing of heart rate data which is sent to the **SensumAPI**

## Input Capture
`public static final String INPUT_CAPTURE = "input-capture"`

This is used to enable/disable capturing of text/emoji data which is sent to the **SensumAPI**

## GSR Capture
`public static final String GSR_CAPTURE = "gsr-capture"`

This is used to enable/disable capturing of GSR data which is sent to the **SensumAPI**

## Re Cancel Capture
`public static final String RE_CANCEL = "re-cancel"`

This is used to check if there is data to send and re-cancel the session 

## Device Disconnected
`public static final String DEVICE_DISCONNECTED = "com.example.bluetooth.le.ACTION_GATT_DISCONNECTED"`

This is used to pass a message from the **SensumSDK** service in case of any device disconnection

## Data Rate Send
`public static final String DATA_RATE_SEND = "send-rate"`

This is used to pass the interval rate (in milliseconds) for the data to be sent to the **SensumAPI**

## API Response
`public static final String API_RESPONSE = "api-response"`

This is used to pass message from the **SensumSDK** service for the **SensumAPI** response

## Toast Message
`public static final String TOAST_MESSAGE = "toast-message"`

This is used to pass informative toast message from the **SensumSDK** service

## Generate Number Of Test Data Records
`public static final String GENERATE_NUMBER_OF_RECORDS = "generate_number_of_records"`

This is used to pass a message to the **SensumSDK** service to get the desired number of test data records from the **SensumAPI**

## Generate Test Data
`public static final int GENERATE_TEST_DATA = 129`

This is used to pass a message to the **SensumSDK** service to get test data from the **SensumAPI**

## Heart Rate Test Data
`public static final String HR_TEST_DATA_FILTER = "hr-test-data-filter"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving the heart rate test data from the **SensumAPI**

## Input Sentiment Text
`public static final int INPUT_SENTIMENT_TEXT = 128`

This is used to filter/pass text & emoji message for sentiment analysis to the **SensumSDK** service

## Emoji Sentiment Filter
`public static final String EMOJI_SENTIMENT_FILTER = "emoji-sentiment-filter"`

This is used to pass Emoji value to the **SensumSDK** service which is passed to the API for Sentiment analysis

## Text Sentiment Filter 
`public static final String TEXT_SENTIMENT_FILTER = "text-sentiment-filter"`

This is used to pass Text value to the **SensumSDK** service which is passed to the API for Sentiment analysis

## Emotionality
`public static final String EMOTIONALITY = "emotionality"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Emotionality value (Sentiment Analysis) from the **SensumAPI**

## Positivity
`public static final String POSITIVITY = "positivity"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Positivity value (Sentiment Analysis) from the **SensumAPI**

## Negativity 
`public static final String NEGATIVITY = "negativity"`

This is used to pass a message from the **SensumSDK** service which is used as an intent filter at the front end for receiving Negativity value (Sentiment Analysis) from the **SensumAPI**

## Connect
`public static final int CONNECT = 101`

This is used to connect to the selected device from the list of the devices

## Connection 
`public static final String CONNECTION = "connection"`

This is used to pass a connection message from the **SensumSDK** service to the front end

## BLE Scan
`public static final int BLE_SCAN = 102`

This is used to pass a BLE scan message to the **SensumSDK** service

## BLE Connection Filter
`public static final String BLE_CONNECTION_FILTER = "ble-connection-filter"`

This is used to pass a BLE connection message from the **SensumSDK** service which is used as an intent filter at the front end

## Bluetooth Scan
`public static final int BLE_SCAN = 107`

This is used to pass a bluetooth scan message to the **SensumSDK** service

## Bluetooth Connection Filter
`public static final String BLUETOOTH_CONNECTION_FILTER = "bluetooth-connection-filter"`

This is used to filter for bluetooth connection at the front end

## Bluetooth Device Filter
`public static final String BLUETOOTH_DEVICE_FILTER = "bluetooth-device-filter"`

This is used to filter for bluetooth device at the front end

## Connect Bluetooth Device
`public static final int CONNECT_BLUETOOTH_DEVICE = 108`

This is used to pass a connect bluetooth device message to the **SensumSDK** service

## Cancel Capture
`public static final int CANCEL_CAPTURE = 112`

This is used to cancel sending of the captured data to the **SensumAPI**

## Start Capture
`public static final int START_CAPTURE = 113`

This is used to start sending of the captured data to the **SensumAPI**

## Hello 
`public static final int HELLO = 127`

This is used for the initial communication between developer and frontend to demo how it works

## Hello Filter 
`public static final String HELLO_FILTER = "hello-filter"`

This is used to filter for hello at the front end

## Cancel Offline Capture
`public static final int CANCEL_OFFLINE_CAPTURE = 132`

This is used to cancel offline capturing of the data

## Start Offline Capture
`public static final int START_OFFLINE_CAPTURE = 133`

This is used to start offline capturing of the data

## Start SDK Server
`public static final String START_SDK_SERVER = "start-sdk-server"`

This is used to start a server locally on the device which listens on port 8080 as a localhost. The server serves the request and returns a json which contains the raw biometric data recorded and the process data returned from the **SensumAPI**

## Disconnect BLE Device
`public static final int DISCONNECT_BLE = 134`

This is used to disconnect a BLE device

## Disconnect Bluetooth Device
`public static final int DISCONNECT_BLUETOOTH = 135`

This is used to disconnect a bluetooth device

## Connected Devices
`public static final int CONNECTED_DEVICES = 136`

This is used to pass a message to the sdk to get the connected device names

## Connected Devices Filter
`public static final String CONNECTED_DEVICES_FILTER = "connected-devices-filter"`

This is used to filter for the connected devices

## BLE Device Name
`public static final String BLE_DEVICE_NAME = "ble-device-name"`

This is used to pass the BLE device name from the **SensumSDK** service

## Bluetooth Device Name
`public static final String BLUETOOTH_DEVICE_NAME = "bluetooth-device-name"`

This is used to pass the bluetooth device name from the **SensumSDK** service




