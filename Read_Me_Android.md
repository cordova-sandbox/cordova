follow : https://codesundar.com/lesson/publish-cordova-apps-to-playstore/

delete previous final and JDRE.apk

if switching from IOS build go to Firebase console/ setting/ general and download/make a googleService-info.plist and add it in the root folder of cordova project

Change id in config.xml to id="com.JDRE.android"

!!!!change versions!!!!

commands:
cordova build --release android

the path for new APK will be platforms/android/app/build/outputs/apk/release

rename unasigned release to JDRE.apk

jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore JDRE.keystore JDRE.apk JDRE

jarsigner: Eightletters1  


./zipalign -v 4 JDRE.apk JDRE-final.apk
