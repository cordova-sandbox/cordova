# Build an Android Cordova app

## To build Android app to phone for tests

1. Navigate to the app folder under JDRE

1. `npm run build-cordova`

1. Then come back to this folder and

1. `cordova build android`

## Guide to deploy an android App : <https://codesundar.com/lesson/publish-cordova-apps-to-playstore/>

1. Delete previous final and JDRE.apk

1. If switching from IOS build go to Firebase console/ setting/ general and download/make a googleService-info.plist and add it in the root folder of cordova project

1. Change id in config.xml to id="com.JDRE.android"

1. Make sure to change versions!!!!

1. Then commands

    * `cordova build --release android`

    * the path for new APK will be platforms/android/app/build/outputs/apk/release

    * move the apk to the root of the file

    * rename unasigned release to JDRE.apk

    * ---do not need to do since it already has keystore file---`keytool -genkey -v -keystore yourappname.keystore -alias yourappname -keyalg RSA -keysize 2048 -validity 10000`

    * `jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore JDRE.keystore JDRE.apk JDRE`

    * ---after the ':' this is the keystore password---`jarsigner: Eightletters1`  

    * ./zipalign -v 4 JDRE.apk JDRE-final.apk

1. Then open the google play store console

1. Go to release management, App releases

1. In the 'Android App Bundles and APKs to add' section click browse files and add the 'JDRE-final.apk'

1. Review all other items on the from, then at the bottom click 'Review'

1. Then after reviewing all items click 'START ROLLOUT TO PRODUCTION'

### Please feel free to add to this
