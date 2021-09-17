airwatch-sdk-plugin
===================

Use this document to install the VMware Workspace One SDK Plugin for Apache Cordova. The plugin helps enterprise app developers add enterprise- grade security, conditional access, and compliance capabilities to mobile applications.

Supported Components
--------------------

This plugin works with the listed component versions.
* Workspace ONE UEM Console 2004 or later
* Android v6.0+ / API Level 23+
* iOS 12.0+ / Xcode 12.4 and 12.5

Initial Setup
-------------

Please find the [Prerequisites](https://github.com/vmwareairwatchsdk/vmware-wsone-sdk-cordova/blob/main/GettingStarted.md) for using the Workspace One SDK Plugin for Apache Cordova.

Installation
------------

To install the plugin, type `cordova plugin add airwatch-sdk-plugin` at the command line. This should be added before any other plugin is added to the app.
**Note:** The download from NPM, usually takes 2-3 minutes on average, over high speed internet connection.

Initialization
--------------

The plugin auto-starts on both Android and iOS devices and it automatically starts the Workspace One SDK. After startup, the functions are available in the **window.plugins.airwatch** object. No other initialization is required to use the documented functions.

To receive events from the SDK, an event listener must be initialized. See "Events" below.

Initialization of the SDK adds the listed features to your application, depending on the configurations set in the SDK profile in the Workspace One UEM Console.
* Application level passcode
* Application level tunneling of network traffic 
* Integrated authentication / single sign on 
* Data loss prevention
    * Disable Screenshot (Android only)
    * Restrict open-in for documents, web links, and email to approved applications only Restrict copy/paste (SDK provides flag value)
    * Restrict access to app when device is offline
* Branding of VMware AirWatch splash screens when SDK application is launched on device

Feature Implementation
-----------------------
Please follow document at [implementation](https://github.com/vmwareairwatchsdk/vmware-wsone-sdk-cordova/blob/main/GettingStarted.md).

### Quick Example

On deviceready, please set the SDK event listener: `window.plugins.airwatch.setSDKEventListener(sdkEventCallback)` . The sdkEventCallback is a function that takes two arguments:
1. A string that holds the name of the event fired.
2. An object that contains the additional info on the event function sdkEventCallback(event, info).

```
function sdkEventCallback(event, info)
{
    /* Check (event === "initSuccess") before using sdk functionalities */
}
```

Release Notes
--------------
1. Latest versions of Workspace ONE SDKs (21.8.1 for iOS and 21.7 for Android).
2. UIWebView references removed from Workspace ONE iOS SDK.


Workspace One SDK Documentation
--------------------------
For further details about the Workspace One SDK, navigate to [Workspace-ONE-SDK](https://my.workspaceone.com/products/Workspace-ONE-SDK) and select the required platform, SDK version and Workspace ONE UEM console version.

License
---------
[VMWare License](https://vdc-download.vmware.com/vmwb-repository/dcr-public/c1dc8d44-8327-451d-9b95-1ecf1c0c03f2/b78c7651-b030-487d-93be-609117f5f935/License.pdf)


Open Source Link
--------------------------
[Open Source](https://www.vmware.com/content/dam/aw-microsites/open-source/assets/open_source_license_AirWatch_SDK_Cordova_Plugin_2.6.0_GA.txt)

Questions and Feedback
----------------------
For any questions/feedback or to report an issue, please reach out to [VMware support teams](https://secure.workspaceone.com/login)
