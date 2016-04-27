#How to: add SDK to Xcode and connect to the cloud
Read [Connecting GRRTC Framework with Your Project](http://192.168.2.155/rwshare2/grrtc/ios/introduce/)

####Getting started

######iOS SDK is really simple to use. You can power up your mobile app with huge amount of awesome communication features & data services in just a few minutes.

######The most common way to interact with GRRTC can be presented with the following sequence of actions:

>1. Initialize framework with application credentials
>2. Login with existing user or register new one
>3. Perform actions with GRRTC communication services and any data entities (users, locations, files, custom objects, pushes etc.)

####Relay on these system frameworks
>VideoToolbox.framework
<br>libc++.dylib
<br>GLKit.framework
<br>CFNetwork.framework
<br>SystemConfiguration.framework
<br>CoreMedia.framework
<br>OpenGLES.framework
<br>QuartzCore.framework
<br>CoreVideo.framework
<br>AVFoundation.framework
<br>CoreAudio.framework
<br>AudioToolbox.framework
<br>CoreGraphics.framework
<br>UIKit.framework
<br>CoreTelephony.framework
<br>MobileCoreServices.framework

####Initialize framework
>>[GRRTC init];
<br>[MessagingApi init];
<br>[ConfigTool init];

####Configurate the service
>It's also easy to configurate your own service. It can be interesting in cases when you build a big system in just a few configuration steps:
>>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_USERNAME minortype:0 configvalue:@"test_user"];
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_PASSWORD minortype:0 configvalue:@"password"];
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_MODE minortype:0 configvalue:@"TCP"];
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_DOMAIN minortype:0 configvalue:@"sip.pfingo.com"];
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_CODECS minortype:0 configvalue:@"ilbc,opus,pcma,pcmu"];
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_ENABLE_ICE minortype:0 configvalue:(is_ICE_Enable ? @"Y":@"N")];
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_IP minortype:0 configvalue:@"sip.pfingo.com"];  //Set VoIP server IP
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_PORT minortype:0 configvalue:@"5060"];          //Set VoIP server port
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_IMS_IP minortype:0 configvalue:@"203.116.114.141"]; //Set IM server IP
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_IMS_PORT minortype:0 configvalue:@"5222"];          //Set IM server port
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_TUNNEL_IP minortype:0 configvalue:@"pptp.pfingo.com"];
<br>[ConfigTool setConfigValue:CONFIGTOOL_MAJOR_SIP_TUNNEL_PORT minortype:0 configvalue:@"443"];

####VoIP login
#####Broadcasts for VoIP event
>Before logging into the VoIP, UI should add the observers below.
>>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(notification_handler_4call:) name:NOTI_CALL_STATUS_CHANGE object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(notification_handler_4login:) name:NOTI_LOGIN_STATUS_CHANGE object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(GRRTCLocalVideoStreamIncomingnotification:) name:NOTI_LOCAL_VIDEO_STREAM_ARRIVED object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(GRRTCRemoteVideoStreamIncomingnotification:) name:NOTI_REMOTE_VIDEO_STREAM_ARRIVED object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(videoViewdidChangeVideoSizeNotification:) name:NOTI_VIDEOVIEW_CHANGE_SIZE object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(handleCallInviteComing:) name:NOTI_CALL_INVITATION object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(handleCallICEReady:) name:NOTI_GRRTC_ICE_READY object:nil];

>Let UI handle the status' change and events' coming.

####Login                                       
Logging in to VoIP service:
>><br>[[GRRTC instance] login];       

####IM login
#####Broadcasts for VoIP event
>Before logging into the IM, UI should add the observers below, let UI handle the change of status and coming events.
>>[[NSNotificationCenter defaultCenter] removeObserver:self name:EVENT_MESSAGE_INCOMING object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(addMessageNotify:) name:EVENT_MESSAGE_INCOMING object:nil];
<br>[[NSNotificationCenter defaultCenter] removeObserver:self name:EVENT_GROUP_CREATE object:nil];
<br>[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(refreshTableView:) name:EVENT_GROUP_CREATE object:nil];

####Login
######Logging into the IM service
>[MessagingApi loginWithUserID:@"test_user" andPassword:@"password"];  

###Read on: iOS SDK documentation (Apple style)
Full reference on classes and protocols used in GRRTC iOS SDK: 
<br>[Ios sdk online reference](/api/ios/masterTOC.html)

####Read on: iOS SDK introduce (MS Office word)
####English:
<br>[IOS_GRRTC_INTRODUCE.docx](/api/ios/IOS_GRRTC_INTRODUCE.docx)

####Chinese:
<br>[IOS_GRRTC_INTRODUCE_CN.docx](/api/ios/IOS_GRRTC_INTRODUCE_CN.docx)

####Download:
<br>[IOS_sdk_download](http://122.248.203.206/downloads/voipdemo_1.0.364.246192402_20151217_151616_demo_doc_lib.tar.bz2)