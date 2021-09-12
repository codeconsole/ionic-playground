# Ionic 6.17.1 Playground

The setup:
```
sdkmanager 'system-images;android-24;google_apis;x86_64'
avdmanager create avd --name Pixel_2_API_24 --package 'system-images;android-24;google_apis;x86_64' --device 'pixel_2'

ionic start angular blank --capacitor --type=angular
ionic start react blank --capacitor --type=react
ionic start vue blank --capacitor --type=vue

cd angular
npm install @capacitor/android && npx cap add android
npm run build
npx cap run android --target=Pixel_2_API_24 #working

cd react
npm install @capacitor/android && npx cap add android
npm run build
npx cap run android --target=Pixel_2_API_24 #working

cd vue 
npm install @capacitor/android && npx cap add android
npm run build
npx cap run android --target=Pixel_2_API_24 #working
```

Worth mentioning (seems not to affect anyting), there is a FAILURE when adding the android platform.

```
npx cap add android
✔ Adding native android project in android in 34.12ms
⠹ add Error running gradle sync 
FAILURE: Build failed with an exception.

* What went wrong:
Executing Gradle tasks as part of an undefined build is not supported. Make sure that you are executing Gradle from a folder within your Gradle project. Your project should have a 'settings.gradle(.kts)' file in the root folder.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 577ms

Unable to infer default Android SDK settings. This is fine, just run npx cap open android and import and sync gradle manually
```

Also worth mentioning, Android < 24 does not work on either platform. 

This is unfortunate because as of September 2021, Android (5.0-6.0) currently represents 8% of the Android market.
https://www.appbrain.com/stats/top-android-sdk-versions

