# Tutorial - Android

## Introduction

This tutorial is designed to assist Android Developers working with the **SensumSDK** and **SensumAPI**.

It is intended to provide a detailed guide to using the **Sensum Emotion AI** toolkit, providing code examples and guidelines for use.

Have fun and enjoy!

## Getting Started

We strongly recommend using Android Studio v2.3.3 and above. We work on Android Studio v2.3.3 at time of our first public **SensumSDK** release.

 * Open Android Studio.
 * Select **New Project** displayed in Figure 1.

 ![Figure 1 - Start New Project](../../images/figure1_android.png "Figure 1 - Start New Project")
#### <p style="text-align: center;">Figure 1 - Start New Project</p>
<br>

 * Provide a name for your project, for example: '*SensumTutorialApplication*', then click **Next** (see Figure 2).

 ![Figure 2 - Create New Project](../../images/figure2_android.png "Figure 2 - Create New Project")
#### <p style="text-align: center;">Figure 2 - Create New Project</p>
<br>

 * Select the **Phone and Tablet**, and **Wear** options from the *Target Android Devices* dialogue window.
 * We recommend you use API 22: Android 5.1 (Lollipop) or greater for best performance (see Figure 3).

 ![Figure 3 - Select Platforms](../../images/figure3_android.png "Figure 3 - Select Platforms")
#### <p style="text-align: center;">Figure 3 - Select Platforms</p>
<br>

 * Click **Next** and select **Empty Activity** as shown in Figure 4.

 ![Figure 4 - Add Activity](../../images/figure4_android.png "Figure 4 - Add Activity")
#### <p style="text-align: center;">Figure 4 - Add Activity</p>
<br>

 * Click **Next** in order to configure the *Empty Activity*, provide an appropriate title for the *Activity* (for example ‘MainActivity’, as shown in Figure 5).

 ![Figure 5 - Customize the Activity](../../images/figure5_android.png "Figure 5 - Customize the Activity")
#### <p style="text-align: center;">Figure 5 - Customize the Activity</p>
<br>

 * Click **Next**, then select **Blank Wear Activity** in the Add an *Activity to Wear* dialogue window (Figure 6).


 ![Figure 6 - Add an Activity to Wear](../../images/figure6_android.png "Figure 6 - Add an Activity to Wear")
#### <p style="text-align: center;">Figure 6 - Add an Activity to Wear</p>
<br>

 * Click **Next**, you will be presented with the *Customize the Activity* dialogue window.  
 * You may optionally alter the default titles of your: *Activity Name*, *Layout Name*, *Round Layout Name*, and *Rectangular Layout Name* (Figure 7).
 * Click **Finish**.

  ![Figure 7 - Customize the Wear Activity](../../images/figure7_android.png "Figure 7 - Customize the Wear Activity")
#### <p style="text-align: center;">Figure 7 - Customize the Wear Activity</p>
<br>

## Managing Project Dependencies

 * From the *File* menu, navigate to *File* > *New* > *New Module* (Figure 8).

  ![ Figure 8 - New Module](../../images/figure8_android.png " Figure 8 - New Module")
#### <p style="text-align: center;"> Figure 8 - Creating A New Module</p>
<br>

 * The *New Module* dialogue window will appear.
 * Select the **Import .JAR/.AAR Package** option (Figure 9).
 * Click **Next**.

  ![ Figure 9 - Import .JAR/.AAR Package](../../images/figure9_android.png " Figure 9 - Import .JAR/.AAR Package")
#### <p style="text-align: center;"> Figure 9 - Import .JAR/.AAR Package</p>
<br>

 * The *Create New Module* dialogue window will appear (shown in Figure 10).
 * In order to successfully create a new module, the developer must locate the necessary **sdk-release.aar** file on their system.


  ![ Figure 10 - Create New Module](../../images/figure10_android.png " Figure 10 - Create New Module")
#### <p style="text-align: center;"> Figure 10 - Create New Module</p>
<br>

 * Once the **sdk-release** file has been located, click **Finish**.

 * In order to link the **sdk-release** file to the project as a dependency, the developer must navigate to *File* > *Project Structure*, from the *File* menu (Figure 11).

  ![Figure 11 - Project Structure](../../images/figure11_android.png "Figure 11 - Project Structure")
#### <p style="text-align: center;">Figure 11 - Project Structure</p>
<br>

 * You will be presented with the *Project Structure* dialogue window.
 * At the left-hand-side of the dialogue, select **mobile** from the *Modules* section.
 * Click the *Dependencies* tab, then click the ‘**+**’ button (top right-hand-side of dialogue), then select the third option: **3 Module Dependency** (Figure 12).

  ![Figure 12 - Module Dependency](../../images/figure12_android.png "Figure 12 - Module Dependency")
#### <p style="text-align: center;">Figure 12 - Module Dependency</p>
</br>

 * You will be presented with the *Choose Modules* dialogue window (Figure 13).

  ![Figure 13 - Choose Modules](../../images/figure13_android.png "Figure 13 - Choose Modules")
#### <p style="text-align: center;">Figure 13 - Choose Modules</p>
<br>

* Select the **sdk-release**, and click **OK**.
* You will return to the *Project Structure* dialogue window, once again, click **OK**.

## Implementing the Shimmer library for GSR values

 *  To import the Shimmer library, repeat the process outlined for importing the **sensumsdk-release**, but instead locate the **shimmersdk-release.aar** file.

## Including Permissions

 * A number of permissions are required to use the Sensum **sdk-release**, shown in Code Snippet 1.
 * Include these permissions within your manifest file (*AndroidManifest.xml*).

 > Code Snippet 1

```xml
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/>
```

## Google Sign-In

 * For more detailed instuctions on how to implement *Google Sign-In* please refer to Google's <a href = "https://developers.google.com/identity/sign-in/android/start-integrating" target="_blank">documentation</a>.

 * For *Google Sign-In*, a *Play Service* dependency needs to be added to Gradle (Code Snippet 2).

> Code Snippet 2

```java
compile 'com.google.android.gms:play-services-auth:+'
```

**NOTE:** As part of the setup procedure you will need to add `apply plugin: 'com.google.gms.google-services'` to your app-level `build.gradle` file. This can have issues building when added at the top of the file so it is advisable to add this entry under the `dependencies` block.

 * As part of enabling *Google APIs* or *Firebase* services in your Android application the `google-services.json` is processed by the `google-services` plugin.
 * The `google-services.json` is created using *Firebase* during enabling *Google Services* for your Android application and is generally placed in the **app/** directory (at the root of the Android Studio app module).
 * For *Google Sign-In* to work with *AWS* authentication, `OAuth 2.0 client ID` (*Google Android Client ID*) is required by *AWS*.
 * The *Google Android Client ID* is created using *Google Developer Console* by providing your Android application package name and the SHA-1 signing-certificate fingerprint from Android Studio.
 * The generated *Google Android Client ID* needs to be given to us for add it to *AWS* for authentication.

 * In the `onCreate()` method of your sign-in `Activity`, the `GoogleSignInOptions` object should be instantiated.
 * This object is used to create the `GoogleApiClient` which is used for accessing the *Google Sign-In API*.
 * The *Google Web Client ID* which is created in the *Google Developer Console* is required during the creation of the *Google Sign-In* object (shown in Code Snippet 3 as the `gso` object).

> Code Snippet 3

```java
GoogleSignInOptions gso = new GoogleSignInOptions.Builder(GoogleSignInOptions.DEFAULT_SIGN_IN)
       .requestEmail()
       .requestProfile()
       .requestIdToken(googleWebClientId)
       .requestServerAuthCode(googleWebClientId)
       .requestId()
       .build();

googleApiClient = new GoogleApiClient.Builder(this)
       .enableAutoManage(this, this )
       .addApi(Auth.GOOGLE_SIGN_IN_API, gso)
       .build();
```


* The *Google Sign-In* needs to be triggered, this is achieved via an *Intent*. Code Snippet 4 illustrates this.

> Code Snippet 4

```java
Intent signInIntent = Auth.GoogleSignInApi.getSignInIntent(googleApiClient);
this.startActivityForResult(signInIntent, RC_SIGN_IN);
```

 * In `onActivityResult`, the *Google Sign-In* results should be handled and upon successful sign-in, the *Google Id Token* and *Google Web Client ID* need to be passed to the **SensumSDK** as a *Bundle*.
 * This *Bundle* is utilised to maintain the capture-session whilst using the **SensumSDK**.  
 * For authentication the **SensumAPI** *base URL*, *key* and *AWS Identity Pool ID* are also needed to be defined and passed as a *Bundle*.
 * The **SensumSDK** *ServiceConstants* are used to pass the authentication parameters to the **SensumSDK** via a *Bundle*.
 * Code Snippet 5 provides an example of this.

#### Bundle Parameters

|Parameter|Type|Description|
|---------|----|-----------|
|`apiBaseUrl`|String|This is the base url for the API, currently this is `http://api.sensum.co/v0`|
|`apiKey`|String|This is the API Key that will be required to access the **SensumAPI**(For trial usage use `PublicDemoKeyForDocumentation`)|
|`identityPoolId`|String|The CognitoIdentityPoolId required to successfully authenticate with the **SensumAPI**. We will provide you with this.|
|`googleIdToken`|String|This is the google id token returned when successfully logged in with a valid Google account|
|`googleWebClientId`&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |String|This is the web client id that was created when you set up sign-in with Google. It can be found in the Credentials page under 'APIs and Service' in the <a href = "https://console.cloud.google.com/home/dashboard?project=firebase-tutorialapplication" target="_blank">Google Cloud Platform</a> page|

> Code Snippet 5

```java
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
   super.onActivityResult(requestCode, resultCode, data);
   if (requestCode == RC_SIGN_IN) {
       GoogleSignInResult result = Auth.GoogleSignInApi.getSignInResultFromIntent(data);
       GoogleSignInAccount acct = result.getSignInAccount();
       String googleIdToken = acct.getIdToken();
       Bundle bundle = new Bundle();
       bundle.putString(API_BASEURL, apiBaseUrl);
       bundle.putString(API_KEY, apiKey);
       bundle.putString(IDENTITY_POOL_ID, identityPoolId);
       bundle.putString(GOOGLE_ID_TOKEN, googleIdToken);
       bundle.putString(GOOGLE_WEB_CLIENT_ID, googleWebClientId);
       sendToService(bundle, GOOGLE_LOGIN);
   }
}
```

## Gradle Dependencies

* Code Snippet 6 displays the Gradle Dependencies that the developer will need to include to successfully run the application.

> Code Snippet 6

```java
compile 'com.amazonaws:aws-android-sdk-core:2.4.+'
compile 'com.amazonaws:aws-android-sdk-s3:2.4.+'
compile 'com.amazonaws:aws-android-sdk-cognito:2.4.+'
compile 'com.amazonaws:aws-android-sdk-ddb:2.4.+'
compile 'com.amazonaws:aws-android-sdk-cognitoidentityprovider:2.4.+'
compile 'com.squareup.retrofit2:retrofit:2.1.0'
compile 'com.squareup.retrofit2:converter-moshi:2.1.0'
compile 'com.squareup.moshi:moshi:1.2.0'
compile 'com.squareup.okhttp3:okhttp:3.4.1'
compile 'com.squareup.okhttp3:logging-interceptor:3.4.1'
compile 'com.google.code.gson:gson:2.8.0'
compile 'com.google.guava:guava:19.0'
```


## Creating a Service

 * The **SensumSDK** runs in the background of the application.
 * The developer is required to create a *ServiceConnection*, that is responsible for communication between the application front-end and the **SensumSDK**.
In order to create this *ServiceConnection*, follow the steps outlined within Code Snippet 7.
 * The developer will need to create an instance of the *Messenger* object.
 * This object has the ability to send *Message* objects to the *Service*.
 * Once the over-ridden `onServiceConnected` method is called, the `Messenger` object is initialised using the passed in `IBinder` object.

> Code Snippet 7

```java
private final ServiceConnection mConnection = new ServiceConnection() {
        @Override
        public void onServiceConnected(ComponentName componentName, IBinder iBinder) {
            mIsBound = true;
            mServiceMessenger = new Messenger(iBinder);
        }

       @Override
        public void onServiceDisconnected(ComponentName componentName) {
            Log.d(TAG, "onServiceDisconnected: ");
        }
    };
```

* Declare both the *Service* and the *BLE Service* within your manifest file (*AndroidManifest.xml*) as shown in Code Snippet 8.

> Code Snippet 8

```xml
<service android:name="co.sensum.sensumservice.SDK.SdkService"/>
<service android:name="co.sensum.sensumservice.SDK.BLE.BluetoothLeService"/>
```

## Binding and Unbinding the Service
 * To bind the *Service* the developer will have to override the `onStart` method and include the lines in Code Snippet 9.

> Code Snippet 9

```java
@Override
protected void onStart() {
    super.onStart();
    Intent intent = new Intent(this, SdkService.class);
    bindService(intent, mConnection, Context.BIND_AUTO_CREATE);
}
```
 * When the app is closed (destroyed) the *Service*  will need to be unbound, otherwise it will continue running (see Code Snippet 10).
 * A boolean variable named `mIsBound` is initialised as **true**, once the *Service* is connected.  
 * When the *Service* is unbound, `mIsBound` is set to **false**.

> Code Snippet 10

```java
@Override
protected void onDestroy() {
    super.onDestroy();
    if (mIsBound) {
        unbindService(mConnection);
        mIsBound = false;
    }
}
```











## Using a Broadcast Receiver

 * A *BroadcastReceiver* ‘listens’ for (receives and handles) *Broadcast Intents*, sent by the *Service*.
 * The *BroadcastReceiver* is essential as it manages messages sent from the **sdk-release**, within the front-end application.
 * The *BroadcastReceiver* makes use of *Filters*, that determine which events the application should ‘listen’ for.
 * The over-ridden method `.onReceive` takes two arguments: *Context* and *Intent*.
 * The *Intent* parameter has an associated action that specifies how the
 *BroadcastReceiver* should behave.
 * Table 1 outlines the filters included in the *Service* and the *Intent Extras* they return.

### Table 1: Broadcast Receiver Filters

|Action|Description|IntentExtras|
|------|-----------|------------|
|**BLE_DEVICE_FILTER**|Filters for BLE devices|`ArrayList<BluetoothDevice>`|
|**VALUE_FILTER**|Filters for heart rate value|`String`|
|**GPS_FILTER**|Filters for GPS values|`Bundle`|
|**ACC_FILTER**|Filters for acceleration values|`Bundle`|
|**DEVICE_DISCONNECTED**|Filters for a device disconnected value|`null`|
|**API_RESPONSE**|Filters for responses from the API|`String`|
|**TOAST_MESSAGE**|Filters for messages from the Service|`String`|
|**CONNECTION_FILTER**|Filters for connection BLE messages|`String`|
|**BLUETOOTH_CONNECTION_FILTER**|Filters for bluetooth connection messages|`String`|
|**BLUETOOTH_DEVICE_FILTER**|Filters for bluetooth devices|`ArrayList<BluetoothDevice>`|
|**GSR_FILTER**|Filters for GSR values|`String`|
|**ACC_FAILED_REGISTERED**|Filters for acceleration failure from unsupported devices|`null`|
|**HELLO_FILTER**|Filters for hello message|`String`|

## Setting up the Broadcast Receiver

  * Code Snippet 11 contains all necessary code that will allow you to setup a *BroadcastReceiver*.

> Code Snippet 11

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
                    isAcc = true;
                    break;
                case VALUE_FILTER:
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
            }
        }
    };
  ```

 * The *BroadcastReceiver* must be registered in order to receive *Intents* from a *Service*.
 * The `registerReceiver` method, takes two arguments: *BroadcastReceiver* and *IntentFilter*.
 * We have included our own method that returns an *IntentFilter:* `getUpdateIntentFilter` (this method is displayed within Code Snippet 13).
 * This method should be called immediately on starting the application, therefore, it is placed within the `.onResume` method, as shown in Code Snippet 12.

> Code Snippet 12

```java
 @Override
    protected void onResume() {
        super.onResume();
        registerReceiver(mMessageReceiver, getUpdateIntentFilter());
    }
```

> Code Snippet 13

```java
  private IntentFilter getUpdateIntentFilter() {
        IntentFilter filter = new IntentFilter();
        filter.addAction(HELLO_FILTER);
        filter.addAction(GPS_FILTER);
        filter.addAction(ACC_FILTER);
        filter.addAction(VALUE_FILTER);
        filter.addAction(GSR_FILTER);
        filter.addAction(API_RESPONSE);
        filter.addAction(TOAST_MESSAGE);
        return filter;
    }
```

 * When the application is destroyed (on application close/force-close), the *BroadcastReceiver* must be unregistered.
 * This is handled via the `.onDestroy` method. Code Snippet 14 demonstrates how to achieve this.

> Code Snippet 14

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

## Communicating with the Service

 * The application’s communication with the *Service* requires that commands be sent via *Message* objects.
 * The *Message* object contains a property called `arg1` (which is an Integer value).
 * This Integer value represents one of the possible options listed in the Constants column of Table 2 (corresponding to an integer value between 0 and 8).
 * This property (`arg1`) will carry the command you want to request from the *Service*.

### Table 2: Send to Service Commands

|Constants (of type 'Int')|Required Bundle Data|
|-------------------------|--------------------|
|**CONNECT**|`String DEVICE_NAME`, <br> `String DEVICE_ADDRESS`|
|**BLE_SCAN**|`null`|
|**START_CAPTURE**|`boolean ACCELERATION_CAPTURE`,<br> `boolean HR_CAPTURE, boolean GPS_CAPTURE`,<br> `boolean INPUT_CAPTURE`,<br> `int DATA_RATE_SAMPLE`,<br> `int DATA_RATE_SEND`|
|**CANCEL_CAPTURE**|`boolean ACCELERATION_CAPTURE`,<br> `boolean HR_CAPTURE`, <br> `boolean GPS_CAPTURE`,<br> `boolean INPUT_CAPTURE`|
|**LOGIN**|`String USER_NAME`,<br> `String PASSWORD`,<br> `String API_BASEURL`,<br> `String AUTH_TOKEN`|
|**GOOGLE_LOGIN**|`String API_BASEURL_IAM`,<br> `String API_KEY`,<br> `String IDENTITY_POOL_ID`,<br> `String GOOGLE_ID_TOKEN`,<br> `String GOOGLE_AUTH_CODE`|
|**INPUT_TEXT**|`String TEXT_MESSAGE`|
|**BLUETOOTH_SCAN**|`null`|
|**CONNECT_BLUETOOTH_DEVICE**|`String DEVICE_NAME`,<br> `String DEVICE_ADDRESS`|
|**HELLO**|`null`|
|**EXPORT_DATABASE**|`null`|
|**DELETE_ALL_DATA**|`null`|

 * This *Message* object also has the capacity to transmit data in the form of a *Bundle*.
 * A *Bundle* contains associated data that can be interpreted by the *Service*.
 * Table 2 indicates the relationship between selected Constants, and the requirements for a *Bundle* of a particular type.
  * e.g. If using the **CONNECT** constant, then the associated *Bundle* should contain two Strings, one for **DEVICE_NAME**, the other for **DEVICE_ADDRESS**.
 * Code Snippet 15 illustrates how to construct a *Message* object, and how to send it on to the *Service*.
 * The *Messenger* object, `mServiceMessenger`, is able to execute its associated `.send` method. This sends the constructed *Message* object to the *Service*.

> Code Snippet 15

 ```java
   public void sendToService(Bundle bundle, int argValue){
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

## Testing the Service

 * To test the service, the developer create a *Button* that will be able to send a *Message* to the *Service*.
 * Within the `onClickListener`, make a call to the `sendToService` method.
 * Enter **null** as the first parameter (*Bundle*) and **HELLO** as the second parameter (*Int*).
 * This will send this *Message* to the *Service*.
 * The *Service* will receive this *Message* and send a *Broadcast*, which the *BroadcastReceiver* will listen for.
 * The *BroadcastReceiver* will handle the *action* and in this case the *action* will fall under the **HELLO_FILTER** case.
 * It is up to the developer what they wish to do with the returned *String*.

> Code Snippet 16

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
                    isAcc = true;
                    break;
                case VALUE_FILTER:
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
            }
        }
    };
```
 * Set up a button in your front-end activity/fragment.
 * Inside the `onClickListener` include the lines shown in Code Snippet 17.

> Code Snippet 17

```java
Button button = (Button) findViewById(R.id.hello_button);
button.setOnClickListener(new View.OnClickListener() {
   @Override
   public void onClick(View view) {
       sendToService(null, HELLO);
   }
});
```

 * Then in the *BroadcastReceiver*, listen for the constant **HELLO_FILTER** (ensure that you are filtering for this in the call to register the receiver).

## Setting up BLE

 * To scan for Bluetooth Low Energy (BLE) devices, the developer will have to create a *Button* object that will tell the *Service* to start scanning.
 * As in the <a href ="#testing-the-service">__Testing the Service__</a> section, the developer should execute the `sendToService` method within the *Button’s* `onClickListener` (refer to Table 2).
 * The first parameter that the `sendToService` method expects in this instance is `null`, as there is no extra data that the Service needs to execute this task.
 * The second parameter that it takes is **BLE_SCAN** (Code Snippet 18).

> Code Snippet 18

```java
Button button = (Button) findViewById(R.id.scanButton);
button.setOnClickListener(new View.OnClickListener() {
   @Override
   public void onClick(View view) {
       sendToService(null, BLE_SCAN);
   }
});
```

## Receiving BLE Devices

 * To receive devices from the *Service* the developer will have to set up the *BroadcastReceiver* to listen for the **BLE_DEVICE_FILTER** constant.
 * Table 1 displays the data that the *Intent* received by the *BroadcastReceiver* carries.
 * In this case, the data that is received is an *ArrayList* of *BluetoothDevices*.
 * It is then up to the developer as to how they wish to display these devices.
 * We would recommend that the user sets up a *ListView* or *RecyclerView*.

## Connecting a BLE Device

 * To connect a BLE device the developer will need to send two *String* objects as part of the *Bundle* object that will be sent to the *Service* as part of the `sendToService` method (Code Snippet 19).
 * According to Table 2, the two Strings required are the BLE device's name and address.
 * These are necessary in order to create a connection between the Android device and the BLE device.
 * The developer should include the **CONNECTION_FILTER** constant within the *BroadcastReceiver’s* overridden `onReceive` method.
 * According to Table 1, the data received is of type *String*.
 * This *String* provides a connection message, sent back from the *Service*, to notify the user whether the connection was successful or not.

> Code Snippet 19

```java
Bundle bundle =  new Bundle();
bundle.putString(ServiceConstants.DEVICE_NAME, deviceName);
bundle.putString(ServiceConstants.DEVICE_ADDRESS, deviceAddress);
sendToService(bundle, CONNECT);
```

* **SensumSDK** supports connecting to BLE devices for reading heart rate measurements. For a list of tested compatible devices please view the <a href = "http://help.sensum.co/knowledge_base/topics/what-type-of-sensors-can-i-use" target="_blank"> list of compatible devices</a> at our Knowledge Centre.

## Receiving Values

 * This version of the **SensumSDK** only returns heart rate values from the BLE device, therefore the developer should ensure that the BLE device that they are using can detect heart rate.
 * On connection the BLE device will send values to the *Service*.
 * The *Service* will then broadcast these values to the application that the developer has built.
 * The developer should include the **VALUE_FILTER** constant within the *BroadcastReceiver’s* `onReceive` method.
 * According to Table 1, the value received will be of type *String*. This value will be the heart rate.

## Bluetooth

 * To scan for, receive, and read values from Bluetooth devices, please follow the steps previously outlined within the <a href = "#setting-up-ble">Setting up BLE</a> section of this tutorial.
 * The same steps should be taken, however bear in mind that the constants should change i.e. replace BLE_SCAN with **BLUETOOTH_SCAN**.
 * This version of the **SensumSDK** will only connect to a *Shimmer 2r* device. This device returns GSR values.
 * The developer should include the **GSR_FILTER** constant within the *BroadcastReceiver’s* `onReceive` method.
 * According to Table 1 the value received will be of type *String*. This value will be the GSR value.



**Note:** This document is regularly updated with new devices. Please contact us for integration details. GSR data is only accessible from *Shimmer 2r* devices at present.

## Receiving GPS and Acceleration Values


 * GPS and Acceleration values will automatically be sent from the *Service* to the application’s frontend once the user has started the application and is authenticated (see <a href = "#google-sign-in">Google Sign-In Section</a>).
 * The developer should include the **GPS_FILTER** and the **ACC_FILTER** constants within the *BroadcastReceiver’s* `onReceive` method.
 * Both of these filters receive a bundle that contains multiple value types.
 * Refer to Table 3 to discover the value types returned from the *Service*.

### Table 3: Broadcast Receiver Filter Examples

|Filter|Bundle|Constants|Example Method Call|
|------|------|---------|-------------------|
|**GPS Filter**|Float speed|SPEED_VALUE|gpsBundle.getFloat(SPEED_VALUE)|
||Double latitude|LATITUDE_VALUE|gpsBundle.getFloat(LATITUDE_VALUE)|
||Double longitude|LONGITUDE_VALUE|gpsBundle.getFloat(LONGITUDE_VALUE)|
||Double altitude|ALTITUDE_VALUE|gpsBundle.getFloat(ALTITUDE_VALUE)|
||Float bearing|BEARING_VALUE|gpsBundle.getFloat(BEARING_VALUE)|
||Float accuracy|ACCURACY_VALUE|gpsBundle.getFloat(ACCURACY_VALUE)|
|**ACC_FILTER**|Float x|X_VALUE|accBundle.getFloat(X_VALUE)|
||Float y|Y_VALUE|accBundle.getFloat(Y_VALUE)|
||Float z|Z_VALUE|accBundle.getFloat(Z_VALUE)|


## Capturing Data

 * Once the developer is able to receive data from the *Service* and is authorised (See <a href ="#google-sign-in">Google Sign-In Section</a>), they can start to send data to the **SensumAPI**.
 * To do this the developer should create a *Button* object that implements the `sendToService` method (See <a href = "testing-the-service">Hello example</a> & <a href ="#table-2">Table 2</a> for more info).
 * The arguments that this method expects are: a *Bundle* object and the **START_CAPTURE** command.
 * This will send a message to the Service to start sending captured data to the **SensumAPI**.
 * The content of Code Snippet 20 displays a method that we have created that returns a bundle holding data relevant to the **START_CAPTURE** command.
 * The data held in this bundle informs the **SensumSDK** which metrics are to be recorded, in addition to the frequency at which these metrics should be sent to the **SensumAPI**.

> Code Snippet 20

```java
public Bundle getCaptureBundle() {
 Bundle bundle = new Bundle();
 bundle.putBoolean(ACCELERATION_CAPTURE, isAcc);
 bundle.putBoolean(HR_CAPTURE, isHr);
 bundle.putBoolean(GPS_CAPTURE, isGps);
 bundle.putBoolean(INPUT_CAPTURE, isInput);
 bundle.putLong(DATA_RATE_SEND, dataRate);
 return bundle;
}
```
* In the same way another *Button* should be created to stop the recording.
* This *Button* should implement the `sendToService` method, the arguments that it expects are identical to those used for the **START_CAPTURE** command (see Code Snippet 21).

> Code Snippet 21

```java
sendToService(getCaptureBundle(), START_CAPTURE);
...
sendToService(getCaptureBundle(), CANCEL_CAPTURE);
```

## Receiving Values from SensumAPI

* Receiving the value from the **SensumAPI** works in the same way as receiving values from a device.
* The *BroadcastReceiver* in your `MainActivity` should implement the ‘filters’ shown in Table 4.

### Table 4: Additional Broadcast Receiver Filters

|Action|(description)|Intent Extras|
|------|------|---------|
|**HR_EVENTS_FILTER**|Filters for heart rate events|`null`|
|**ACC_EVENT_FILTER**|Filters for acceleration events|`null`|
|**AROUSAL_EVENT_FILTER**|Filters for arousal events|`null`|
|**GPS_EVENT_FILTER**|Filters for GPS events|`null`|
|**GSR_EVENT_FILTER**|Filters for GSR events|`null`|
|**EMOJI_SENTIMENT_FILTER**|Filters for Emoji Sentiment values|`Bundle`|
|**TEXT_SENTIMENT_FILTER**|Filters for Text Sentiment values|`Bundle`|

* These filters should also be added to your `getUpdateFilter` method (Code Snippet 22).

> Code Snippet 22

```java
private IntentFilter getUpdateIntentFilter() {
      IntentFilter filter = new IntentFilter();
      filter.addAction(HELLO_FILTER);
      filter.addAction(GPS_FILTER);
      filter.addAction(ACC_FILTER);
      filter.addAction(VALUE_FILTER);
      filter.addAction(GSR_FILTER);
      filter.addAction(API_RESPONSE);
      filter.addAction(TOAST_MESSAGE);
      filter.addAction(HR_EVENTS_FILTER);
      filter.addAction(ACC_EVENT_FILTER);
      filter.addAction(AROUSAL_EVENT_FILTER);
      filter.addAction(GPS_EVENT_FILTER);
      filter.addAction(GSR_EVENT_FILTER);
      filter.addAction(EMOJI_SENTIMENT_FILTER);
      filter.addAction(TEXT_SENTIMENT_FILTER);
      return filter;
  }
```

## Realm Queries

* *Realm* is a Mobile Database that provides an alternative to *SQLite* & *Core Data*.
* We use *Realm* to safely and efficiently store/query data from the response the **SensumAPI** returns. We recommend you take some time to study the RealmDocs <a href = "https://realm.io/docs/java/latest/" target="_blank"> here</a>.
* A significant advantage for developers using the **SensumSDK** is the ability to query the *Realm* database from the front-end to see what data has been captured/stored.
* When an event has been received by the *BroadcastReceiver*, the developer can query the *Realm* database to retrieve the values received from the **SensumAPI**.
* The **AROUSAL_EVENT_FILTER** lets the developer know that the **SensumSDK** has received an ‘arousal event’.
* Code Snippet 23 displays how the developer could query *Realm* to see the values stored.

> Code Snippet 23

```java
private void queryRealmForArousalStats() {
   try {
       realm = Realm.getDefaultInstance().getDefaultInstance();
       RealmResults<ArousalStats> realmResults = realm.where(ArousalStats.class).findAll();
       realmResults.load();
       if (!realmResults.isEmpty()) {
           for (ArousalStats realmRecords : realmResults) {
               updateArousalStats(realmRecords);
           }
       } else {
           Log.d(TAG, "No arousal stats data found in the database");
       }
   } catch (Throwable e) {
       Log.d(TAG, "Unable to get arousal stats data from the database " + e.toString());
   }
}

private void updateArousalStats(ArousalStats arousalStats) {
   ArousalSectors arousalSectors = arousalStats.getArousalSectors();
   double activated = arousalSectors.getActivated();
   double calm = arousalSectors.getCalm();
   double excited = arousalSectors.getExcited();
   double passive = arousalSectors.getPassive();
   double relaxed = arousalSectors.getRelaxed();

}

```

* Code Snippet 23 shows the `ArousalStats` object.
* Each record of the object has associated values attached, displayed in the `updateArousalStats` method.

* Tables 5 - 12 display the *Realm* objects that the **SensumSDK** holds.
* These objects contain methods and values associated with the response from the **SensumAPI**.

### Table 5: Example Event Realm Object

| Realm Object                                  | Associated Methods | Method Type | Description                                                                                |
|-----------------------------------------------|--------------------|-------------|--------------------------------------------------------------------------------------------|
| `ResHeartRate` Events associated with Heart Rate | `getValue()`         | String      | Retrieves a value associated with the event event - min, max, normal, rising, falling      |
|                                               | `getTime()`          | long        | Event time                                                                                 |
|                                               | `getSeverity()`      | double      | How much of value change between forward/backward events with respect to the average value |

### Table 6: SensumSDK Realm Objects
| Realm Event Objects |
|---------------------|
| `ResAccelerometerX`   |
| `ResAccelerometerY`   |
| `ResAccelerometerZ`   |
| `ResGpsAccuracy`      |
| `ResGpsAltitude`      |
| `ResGpsBearing`       |
| `ResGpsLatitude`      |
| `ResGpsLongitude`     |
| `ResGpsSpeed`         |
| `ResGSR`              |

### Table 7: Example Statistics Object

| Realm Object   | Associated Methods | Method Type | Description                               |
|----------------|--------------------|-------------|-------------------------------------------|
| `HeartRateStats` | `getAvg()`           | Double      | Returns an average value                  |
|                | `getDuration()`      | Double      | Returns duration value                    |
|                | `getMax()`           | Double      | Returns max value                         |
|                | `getMin()`           | double      | Returns min value                         |
|                | `getPercentiles()`   | Percentiles | Returns a percentile object (see Table 9) |
|                | `getStd()`           | Double      | Returns a standard deviation value        |

### Table 8: SensumSDK Statistics Objects

| Realm Stats Objects |
|---------------------|
| `AccelerometerXStats` |
| `AccelerometerYStats` |
| `AccelerometerZStats` |
| `GpsAccuracyStats`    |
| `GpsAltitudeStats`    |
| `GpsBearingStats`     |
| `GpsLatitudeStats`    |
| `GpsLongitudeStats`   |
| `GpsSpeedStats`       |
| `GsrStats`            |



### Table 9: SensumSDK Percentiles Object

| Object      | Associated Methods | Type   | Description                   |
|-------------|--------------------|--------|-------------------------------|
| `Percentiles` | `get10()`            | double | Returns 10th percentile value |
|             | `get50()`            | double | Returns 50th percentile value |
|             | `get90()`            | double | Returns 90th percentile value |


### Table 10: ArousalStats Realm Object

| Realm Stats Object | Associated Methods | Type           | Description                                                             |
|--------------------|--------------------|----------------|-------------------------------------------------------------------------|
| `ArousalStats`       | `getValue()`         | double         | Returns an activation value                                             |
|                    | `getDominant()`      | String         | Label of the dominant classification category                           |
|                    | `getSectors()`       | ArousalSectors | Returns the sectors associated with the arousal stats object (Table 12) |

### Table 11: EngagementStats Realm Object

| Realm Stats Object | Associated Methods | Type              | Description                                                             |
|--------------------|--------------------|-------------------|-------------------------------------------------------------------------|
| `EngagementStats`    | `getValue()`         | double            | Returns an activation value                                             |
|                    | `getDominant()`      | String            | Label of the dominant classification category                           |
|                    | `getSectors()`       | EngagementSectors | Returns the sectors associated with the arousal stats object (Table 12) |

### Table 12: ArousalSectors and EngagmentSectors Realm Objects

| Object                            | Associated Methods | Type   | Description                                 |
|-----------------------------------|--------------------|--------|---------------------------------------------|
| `ArousalSectors` and `EngagmentSectors` | `getExcited()`       | double | Returns a value associated with excitement  |
|                                   | `getActivated()`     | double | Returns a value associated with activity    |
|                                   | `getCalm()`          | double | Returns a value associated with calmness    |
|                                   | `getPassive()`       | double | Returns a value associated with passiveness |
|                                   | `getRelaxed()`       | double | Returns a value associated with relaxation  |


* Sentiment values are returned via the *BroadcastReceiver* (see Table 4).
* When the developer sends a message to the service using the **INPUT_TEXT** command, the associated *String* object that is sent to the *Service* (see Table 2) is also sent to the **SensumAPI**, before a value is returned to the **SensumSDK**.
* Depending on the type of input (i.e. text or emoji), a *Bundle* is returned to the front-end.
* To receive this bundle the developer should include the **TEXT_SENTIMENT_FILTER** and **EMOJI_SENTIMENT_FILTER**  within the BroadcastReceivers `onReceive` method.

<!-- TEST COMMENT FOR GIT ISSUE-->

* The *Bundle* contains three values of type double (see Table 13).

### Table 13: Sentiment Filter Data

| Object       | Type   | Description                                  |
|--------------|--------|----------------------------------------------|
| `EMOTIONALITY` | double | Returns a value associated with emotionality |
| `POSITIVITY`   | double | Returns a value associated with positivity   |
| `NEGATIVITY`   | double | Returns a value associated with negativity   |

* These events are returned via a *BroadcastIntent* rather than retrieved from the *Realm* database; therefore they should be listened for in the *BroadcastReceiver*'s `onReceive` method.


<!-- NEW EDITS FINISH HERE-->
* The values returned can be used to display data in a variety of ways.
* We recommend using a charting library to show this data coming in from the **SensumSDK**.
* To access these objects the developer should query the *Realm* database (see previous example in Code Snippet 18) to access the desired values.
