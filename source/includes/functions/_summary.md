# Summary Guide

## API Control

### Setting Data Sending Request Rate to the API

#### Android

When using the `sendToService` method ensure that you send the integer parameters **DATA_RATE_SEND** as part of your bundle.

### Listen for API events

#### Android

Use a Broadcast Receiver

 * A *BroadcastReceiver* ‘listens’ for (receives and handles) *Broadcast Intents*, sent by the *Service*.
 * The *BroadcastReceiver* is essential as it manages messages sent from the **sdk-release**, within the front-end application.
 * The *BroadcastReceiver* makes use of *Filters*, that determine which events the application should ‘listen’ for.
 * The over-ridden method *.onReceive* takes two arguments: *Context* and *Intent*. The *Intent* parameter has an associated action that specifies how the
 *BroadcastReceiver* should behave.
 * Table 1 outlines the filters included in the *Service* and the *Intent Extras* they return.

Table 1

|Action|Description|IntentExtras|
|------|-----------|------------|
|**BLE_DEVICE_FILTER**|Filters for BLE devices|`ArrayList<BluetoothDevice>`|
|**HR_FILTER**|Filters for heart rate value|`String`|
|**GPS_FILTER**|Filters for GPS values|`Bundle`|
|**ACC_FILTER**|Filters for acceleration values|`Bundle`|
|**DEVICE_DISCONNECTED**|Filters for a device disconnected value|`null`|
|**API_RESPONSE**|Filters for responses from the API|`String`|
|**TOAST_MESSAGE**|Filters for messages from the Service|`String`|
|**BLE_CONNECTION_FILTER**|Filters for connection BLE messages|`String`|
|**BLUETOOTH_CONNECTION_FILTER**|Filters for bluetooth connection messages|`String`|
|**BLUETOOTH_DEVICE_FILTER**|Filters for bluetooth devices|`ArrayList<BluetoothDevice>`|
|**GSR_FILTER**|Filters for GSR values|`String`|
|**ACC_FAILED_REGISTERED**|Filters for acceleration failure from unsupported devices|`null`|
|**HELLO_FILTER**|Filters for hello message|`String`|
|**HR_EVENT_FILTER**|Filters for heart rate events from the API|`String`|
|**AROUSAL_FILTER**|Filters for heart rate arousals from the API|`String`|
|**GSR_EVENT_FILTER**|Filters for GSR events from the API|`String`|
|**EMOJI_SENTIMENT_FILTER**|Filters for emoji sentiment from the API|`String`|
|**TEXT_SENTIMENT_FILTER**|Filters for text sentiment from the API|`String`|


## Setting up the Broadcast Receiver

  * Code Snippet 1 contains all necessary code that will allow you to setup a *BroadcastReceiver*.

  > Code Snippet 1

  ```java
    private BroadcastReceiver mMessageReceiver = new BroadcastReceiver() {
        @Override
        public void onReceive(Context context, Intent intent) {
            String action = intent.getAction();
            switch (action){
                case HELLO_FILTER:
                    Toast.makeText(MainActivity.this, intent.getStringExtra(EXTRA_DATA), Toast.LENGTH_LONG).show();
                    break;
                case GPS_FILTER:
                    Bundle gpsBundle = intent.getBundleExtra(EXTRA_DATA);
                    break;
                case ACC_FILTER:
                    Bundle accBundle = intent.getBundleExtra(EXTRA_DATA);
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
            }
        }
    };
  ```

 * The *BroadcastReceiver* must be registered in order to receive *Intents* from a *Service*.
 * The *registerReceiver* method, takes two arguments: *BroadcastReceiver* and *IntentFilter*.
 * We have included our own method that returns an *IntentFilter:* `getUpdateIntentFilter()` (this method is displayed within Code Snippet 3).
 * This method should be called immediately on starting the application, therefore, it is placed within the `.onResume()` method, as shown in Code Snippet 2.

> Code Snippet 5

```java
 @Override
    protected void onResume() {
        super.onResume();
        registerReceiver(mMessageReceiver, getUpdateIntentFilter());
    }
```

> Code Snippet 3

```java
  private IntentFilter getUpdateIntentFilter() {
        IntentFilter filter = new IntentFilter();
        filter.addAction(HELLO_FILTER);
        filter.addAction(GPS_FILTER);
        filter.addAction(ACC_FILTER);
        filter.addAction(HR_FILTER);
        filter.addAction(GSR_FILTER);
        filter.addAction(API_RESPONSE);
        filter.addAction(TOAST_MESSAGE);
        filter.addAction(HR_EVENT_FILTER);
        filter.addAction(AROUSAL_FILTER);
        filter.addAction(GSR_EVENT_FILTER);
        filter.addAction(EMOJI_SENTIMENT_FILTER);
        filter.addAction(TEXT_SENTIMENT_FILTER);
        return filter;
    }
```

 * When the application is destroyed (on application close/force-close), the *BroadcastReceiver* must be unregistered. This is handled via the `.onDestroy()` method.
Code Snippet 4 demonstrates how to achieve this.

> Code Snippet 4

```java
    @Override
    protected void onDestroy() {
        super.onDestroy();
        if (mIsBound){
            unbindService(mConnection);
            mIsBound = false;
            unregisterReceiver(mMessageReceiver);
        }
    }
```

## Accelerometer Control

### Start Recording

#### Android

Use the `sendToService` method the the boolean `ACCELERATION_CAPTURE = true` with the constant **START_CAPTURE** to the background service.

### Stop Recording

#### Android

Use the `sendToService` method the the boolean `ACCELERATION_CAPTURE = true` with the constant **CANCEL_CAPTURE** to the background service.

### Check API Sending status


#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up using **API_RESPONSE** intent to handle **SensumAPI** responses.

### Assign Listener

#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up to handle Accelerometer data using the **ACC_Filter** intent.

### Set Read Frequency

#### Android

* When sending the **START_CAPTURE** message to the service using the `sendToService` method, Set the rate of capture using the integer variable DATA_RATE_SEND, while the boolean **ACCELERATION_CAPTURE** is **true**.

## Location Control

### Start Recording

#### Android

Use the `sendToService` method the the boolean `GPS_CAPTURE = true` with the constant **START_CAPTURE** to the background service.

### Stop Recording

#### Android

Use the `sendToService` method the the boolean `GPS_CAPTURE = true` with the constant **CANCEL_CAPTURE** to the background service.

### Check API Sending status


#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up using **API_RESPONSE** intent to handle **SensumAPI** responses.

### Assign Listener


#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up to handle location data using the **GPS_Filter** intent.

### Set Read Frequency

#### Android

* When sending the **START_CAPTURE** message to the service using the `sendToService` method, Set the rate of capture using the integer variable DATA_RATE_SAMPLE, while the boolean **GPS_CAPTURE** is `true`.

## Tag Control

### Start Recording

#### Android

Use the `sendToService` method the the boolean `INPUT_CAPTURE = true` with the constant **START_CAPTURE** to the background service.

### Stop Recording

#### Android

Use the `sendToService` method the the boolean `INPUT_CAPTURE = true` with the constant **CANCEL_CAPTURE** to the background service.

### Check API Sending status

#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up using **API_RESPONSE** intent to handle **SensumAPI** responses.

### Assign Listener

#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up to handle text tag data using the **TEXT_SENTIMENT_FILTER** intent.
* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up to handle emoji tag data using the **EMOJI_SENTIMENT_FILTER** intent.

### Create Tag

#### Android

* When sending the **INPUT_SENTIMENT_TEXT** message to the service using the `sendToService` method, add the string parameter TEXT_MESSAGE.

## Bluetooth Control

### Start Recording

#### Android

Use the `sendToService` method the the boolean `HR_CAPTURE = true` with the constant **START_CAPTURE** to the background service.

### Stop Recording

#### Android

Use the `sendToService` method the the boolean `HR_CAPTURE = true` with the constant **CANCEL_CAPTURE** to the background service.

### Check API Sending status

#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up using **API_RESPONSE** intent to handle **SensumAPI** responses.

### Assign Listener

#### Android

* Create a <a href = "#use-a-broadcast-receiver">Broadcast Receiver</a>, setting it up to handle bluetooth data using the **BLE_DEVICE_FILTER**, **BLE_CONNECTION_FILTER**, **BLUETOOTH_DEVICE_FILTER**, **BLUETOOTH_CONNECTION_FILTER** and **DEVICE_DISCONNECTED** intents.

### Scan for Devices

#### Android

 * Use the `sendToService` method with the constant **BLE_SCAN** or **BLUETOOTH_SCAN**, depending on if the device is compatible with Bluetooth LE or standard, to send the command to the background service.

### Connect to Device

#### Android
 * Use the `sendToService` method with the constant **CONNECT_BLE** or **CONNECT_BLUETOOTH_DEVICE**, depending on if the device is compatible with Bluetooth LE or standard, as well a bundle containg the string variables **DEVICE_NAME** and **DEVICE_ADDRESS** to send the command to the background service.

### Disconnect From Device

#### Android

* Use the `sendToService` method with the constant **DISCONNECT_BLE** or **DISCONNECT_BLUETOOTH**, depending on if the device is compatible with Bluetooth LE or standard, as a bundle to the background service.
