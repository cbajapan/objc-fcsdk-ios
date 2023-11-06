# Objective-C FCSDK iOS

## System Minimum Requirements ##
* Xcode 13
* Monterey 12.1
* swift-tools-version:5.3
* iOS 13

## Binaries
| **Platform / arch** | arm64  | x86_x64 |
|---------------------|--------|---------|
| **iOS (device)**    |   ✅   |   N/A   |
| **iOS (simulator)** |   ✅   |    ✅   |


#### Please Follow this repository for the lateset SDK notifications.
By default Bitcode is enabled in FCSDKiOS. If you want your app to have bitcode enabled all the other frameworks and libraries you depend on, also need to have bitcode enabled. 

## License 

 See - **Commercial** - License.txt

## Installation

### Swift Package Manager 
 
    1. In your Xcode Project, select File > Swift Packages > Add Package Dependency.
    2. Follow the prompts using the URL for this repository
    3. Choose which version you would like to checkout(i.e. 3.4.6)

You will need to make sure that the binary is linked with the target you want to use the CocoaPod in.
Navigate to Workspace -> Targets -> Build Phases -> Link Binaries With Libraries and add ACBClientSDK.

## Importing FCSDKiOS

### Note

Starting in FCSDKiOS version 3.4.4, we’ve switched to a dynamic framework, the `import` mechanism needs to change. Please import the SDK accordingly.

```Objective-C
@import ACBClientSDK;
``` 

### CocoaPods

Check out [Get Started](http://cocoapods.org/) tab on [cocoapods.org](http://cocoapods.org/).

To use FCSDKiOS in your project add the following 'Podfile' to your project

    platform :ios, '10.0'
    use_frameworks!

    pod 'ACBClientSDK'

Then run:

    pod install
 
You will need to make sure that the binary is linked with the target you want to use the CocoaPod in.
Navigate to Workspace -> Targets -> Build Phases -> Link Binaries With Libraries and add ACBClientSDK.xcframwork.

You will then need to add a WebRTC Library to resolve the symbols is the SDK. We recommend using CBARealTime Swift Package. 


### Simulator Support
We now offer simulator support with FCSDKiOS. It is simple to set up. The Simulator does not support the use of the camera, therefore we need to give it a video to stream to your real device.

1. Create a short placeholder video about (5 seconds long) and name it `Simulator.mp4`.

2. Drag and Drop the `.mp4` into the root level of your application 

3. Make sure you select `copy items if needed` and select the `target` you wish to add the video to.

That's it now when you make calls with the simulator, you will see the video from your real device and the mp4 will stream from the simulator. 
 
### Known issues
* Sometimes when the CocoaPod is installed, it will try to Link Pod_YourApp.framework to the target. Simply remove Pod_YourApp.framework from the Link Binaries With Libraries section in the App's Target
