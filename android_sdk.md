# Download Android SDK & Code Samples

[android sdk download](/downloads/Grrtc_SDK_Android.zip)


# How to: add SDK to IDE

## 1. Import Jar Files

Importing files to your project path: app->libs needs jars file(grrtc-android-sdk/jars).

We provide other jars:

	grrtc_api.jar
	fileutil.jar

Grrtc Android SDK uses other external libs: 

	xutils3.0
	play-services-gcm
	picasson
	photoView

You should add the libs' dependencies in you app's build.gradle like:

	dependencies 
	{
		compile 'com.google.android.gms:play-services-gcm:8.3.0'
		compile 'org.xutils:xutils:3.1.+'
		compile 'com.squareup.picasso:picasso:2.4.0'
		compile 'com.commit451:PhotoView:1.2.4'
	}

## 2. Import dynamic library files

You should import file(grrtc-android-sdk/so) to your project with this path: jniLibs->armeabi-v7a

We provide the files below for you:

	libgrrtcapi.so
	libjingle_peerconnection_so.so

## 3. Import config file 

You need to import config file (grrtc-android-sdk/config) to your assets path.
We provide the config file below: 

	configall.cfg


# Getting started

Android SDK is very simple to use. You can power up your mobile app with huge amount of awesome communication features & data services in just a few minutes.

## Brief introduce 
The most common way to interact with grrtc can be presented with the following sequences:

	1. Initialize frameworks before apllications start
	2. Login with existing user or regist a new one
	3. Launch a call or start chatting

### Initialize frameworks

	CallApi.init(this);
		
	MessagingApi.init(this);
Before you start applications, init phonecall and message frameworks first.

### login to the server

    LoginApi.login(username, password);

You can also regist the local broadcast to get login result from the server like 

    LocalBroadcastManager.getInstance(this).registerReceiver

	(LoginStatusChangedReceiver,new IntentFilter

	(LoginApi.EVENT_LOGIN_STATUS_CHANGE));
  
	private BroadcastReceiver LoginStatusChangedReceiver = new BroadcastReceiver() {
		@Override
		public void onReceive(Context context, Intent intent) {
			
			int new_status = intent.getIntExtra(LoginApi.PARAM_LOGIN_STATUS, -1);

			switch (new_status) {
			
			case LoginApi.STATUS_REGISTER_OK:
		       // login successful 

				break;
			}
		}
	};

### launch a call or start a chat

 if you can login to the server successfully, you can lauch a sip  call like

    CallApi.initiateAudioCall(CalleeNumber);

or send a text message to other users

    conversation.sendText(messageContent)

### others
 if you want to use google cloud message function, you should get google-services.json from the link below:

[cloud-messaging](https://developers.google.com/cloud-messaging/android/start)

add this content to your AndroidManiest.xml

 		
 	<!-- [START gcm_receiver] -->
        <receiver
            android:name="com.google.android.gms.gcm.GcmReceiver"
            android:exported="true"
            android:permission="com.google.android.c2dm.permission.SEND" >
            <intent-filter>
                <action android:name="com.google.android.c2dm.intent.RECEIVE" />
                <category android:name="gcm.play.android.samples.com.gcmquickstart" />
            </intent-filter>
        </receiver>
        <!-- [END gcm_receiver] -->

        <!-- [START gcm_listener] -->
        <service
            android:name="com.globalroam.voipapi.gcm.MyGcmListenerService"
            android:exported="false" >
            <intent-filter>
                <action android:name="com.google.android.c2dm.intent.RECEIVE" />
            </intent-filter>
        </service>
        <!-- [END gcm_listener] -->
        <!-- [START instanceId_listener] -->
        <service
            android:name="com.globalroam.voipapi.gcm.MyInstanceIDListenerService"
            android:exported="false">
            <intent-filter>
                <action android:name="com.google.android.gms.iid.InstanceID"/>
            </intent-filter>
        </service>
        <!-- [END instanceId_listener] -->
        <service
            android:name="com.globalroam.voipapi.gcm.RegistrationIntentService"
            android:exported="false">
        </service>
     <meta-data
            android:name="com.globalroam.grrtcapi.API_KEY"
            android:value="add_your_apikey_here" />
        <meta-data
            android:name="com.globalroam.grrtcapi.SECRET_KEY"
            android:value="add_your_secretkey_here" />
Read on: Android SDK documentation (Javadoc)

# Android SDK online api references

Full references on classes and interfaces used in Grrtc Android SDK: 

  [Grrtc Android SDK framework documentation](/api/android/index.html)

Transition guide from 1.0.0 to 1.0.1 version

# Framework changelog:

##v1.0.1 — DEC 1 2015

	added the function of sending files and sending images' function
 
| Col 1   | Col 2                                              |
|======== |====================================================|
|**bold** | ![Valid XHTML] (http://w3.org/Icons/valid-xhtml10) |
| Plain   | Value                                              |