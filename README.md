## To build to iOS device:

### If you have not already:
1. run `xcode-select --install` and agree to prompt to install CLI tools
1. run `npm i -g ios-deploy`


### Then:
1. go to Firebase console/ setting/ general and download/make a googleService-info.plist and add it in the root folder of cordova project !!dont forget to switch them wehn building to a different platform!!
1. change id in config.xml to id in googleService-info.plist (id="com.JDREapp.ios")
1. run `cordova platform add ios`
1. run `cordova plugin add cordova-plugin-firebase cordova-plugin-geolocation cordova-plugin-inappbrowser cordova-plugin-whitelist cordova-plugin-device`
1. in javascript project, include and run script to build to cordova/www directory
1. once www has been built, in cordova directory run `cordova build ios`. You may see "ARCHIVE FAILED" in the terminal. Proceed anyway.
1. run `open ./platforms/ios/JDRE.xcworkspace/`
1. Xcode will open. Select your directory from the list on the left side. Then add your team.
1.  To add notifications make sure you are admin in your ios team and follow https://medium.com/@felipepucinelli/how-to-add-push-notifications-in-your-cordova-application-using-firebase-69fac067e821 to get certifications
1. enter new name, version, and geolocation prompt in config.xml
1. if using inline YouTube videos, include whitelist plugin and `allow-navigation` tag
1. at the top of the screen, select the device/emulator you want to build to, then hit the "play" button.

In Cordova, you can run into many unexpected problems. Here are some relevant solutions we found:
* For issues with the `npm i -g ios-deploy` command: https://github.com/ios-control/ios-deploy/issues/346
* If you can't find your device under the "Develop" menu in Safari or if dev tools pop up and close immediately, the problem may be that device and/or Mac are at 100% battery. Another possible solution is to hard quit Safari, disconnect the phone, restart Safari, and then plug in phone. Then build again from Xcode.

## Debugging

In order to get dev tools:
1. On your phone, go to Settings. Find Safari, and under the "Advanced" menu, turn "Web Inspector" on.
1. On your Mac, open Safari. Choose "Preferences" from the "Safari" menu, and under the "Advanced" tab, turn "Show Develop Menu" on.
1. Under the "Develop" menu, choose your device.

## Get App ready for build
1. add Team to xCode


## Usefull tips/solutions:
1. When building for IOS, you might exprience delay when clicking on buttons or input fields. especcially on IOS 11.3 / .4 the solution that worked for us was to install this fork of fastclick npm package: https://github.com/lasselaakkonen/fastclick.   To install a fork run the following in you app : `npm i lasselaakkonen/fastclick` 
1. to add icons for ios and android, use https://github.com/AlexDisler/cordova-icon
