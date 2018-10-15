# Build an Android Cordova app

## To build Android app to phone for tests

1. Navigate to the app folder under JDRE

1. `npm run build-cordova`

1. Then come back to this folder and

1. `cordova build android`

## Guide to deploy an android App : <https://codesundar.com/lesson/publish-cordova-apps-to-playstore/>

1. Delete previous final and JDRE.apk

1. * If switching from IOS build go to Firebase console/ setting/ general and download/make a googleService-info.plist and add it in the root folder of cordova project

1. Change id in config.xml to id="com.JDRE.android"

1. Make sure to change versions!!!!

1. Then commands

    * `cordova build --release android`

    * the path for new APK will be platforms/android/app/build/outputs/apk/release

    * rename unasigned release to JDRE.apk

    * `jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore JDRE.keystore JDRE.apk JDRE`

    * `jarsigner: Eightletters1`  

    * ./zipalign -v 4 JDRE.apk JDRE-final.apk
