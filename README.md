## To build to iOS device:

### If you have not already:
1. run `xcode-select --install` and agree to prompt to install CLI tools
1. run `npm i -g ios-deploy`

### Then:
1. run `cordova platform add ios`
1. run `cordova plugin add cordova-plugin-firebase cordova-plugin-geolocation cordova-plugin-inappbrowser cordova-plugin-whitelist cordova-plugin-device`
1. in javascript project, include and run script to build to cordova/www directory
1. once www has been built, in cordova directory run `cordova build ios`. You may see "ARCHIVE FAILED" in the terminal. Proceed anyway.
1. run `open ./platforms/ios/<YOUR APP NAME HERE>.xcworkspace/`
1. Xcode will open. Select your directory from the list on the left side. Then add your team.
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
1. follow https://medium.com/@felipepucinelli/how-to-add-push-notifications-in-your-cordova-application-using-firebase-69fac067e821 to get permissions for notifications
1. enter new name, version, and geolocation prompt in config.xml
1. if using inline YouTube videos, include whitelist plugin and `allow-navigation` tag