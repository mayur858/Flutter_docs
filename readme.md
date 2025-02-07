# This is Documentation for reviving the flutter project 

I hope this Documentaion will help you revive you project and would make sure that you are able to run and build you apk for release.

Assume that the project you want to get to working is old or in technical term have depreicated dependencies that are not compatible with the current SDK require 
with flutter you will have to make sure that you change these two file before going ahead as you try to build or run the flutter project flutter itself will show 
you warning that you might want to keep an eye for it will tell you which ***compileSdk** or ***miniSdkVersion*** or ***targetSdkVersion*** version is require.

With this information you can manually have change in build.gradle file in android/app/build.gradle file or in build.gradle file in gradle/settings.gradle file 
after making the changes you need to run the follwoing command so that flutter would acquire the Sdk's that you mention in the above file and would be able to 
make the error resolve.

here are the command in this sequence you need to run them:

```
flutter clean 

flutter pub get

```

These command will delete the the android folder other dependencies and would reinstall them using the ***flutter pub get*** command, moving on will need to 
resolve the pubspec.yaml file some of the dependencies are depreicated or are out of the order, what I mean by this is that they are no longer being maintain by 
the maintainer or the dependencies is not up to the standard of the flutter SDK require it to run or have some null saftey issue.


Now comes the difficult part you will need to run and check the error in order to resolve the dependencies issue as updating all of them at the same time would 
make some of them depreicated or unusable for the project if you still want to take that risk here is the command for it.

```
flutter pub update major

```

but I would highly recommend the one at the time method as it would make reverting back much more easier, but if you have git installed on you system you can just 
revert back to the changes instantly.

```
Note: Some input files use or override a deprecated API.
Note: Recompile with -Xlint:deprecation for details.
Note: C:\Users\kmayu\AppData\Local\Pub\Cache\hosted\pub.dev\image_cropper-7.1.0\android\src\main\java\vn\hunghd\flutter\plugins\imagecropper\ImageCropperDelegate.java uses or overrides a deprecated API.
Note: Recompile with -Xlint:deprecation for details.
```

Lets take the example of the above error in the terminal that would help how to debug the error itself in these error you can clearly see that there is a mention 
of dependencies how do i know that just look at the \Pub directory which can conclude that it is dependecies issue to resolve that specific dependecies issue you 
would need to run the following command.

```
flutter pub add name_of_dependency
```

you might have a question right now why not use the ***update** keyword in command because you are not sure that the sdk that you are running is either going to 
update it to the most latest version or just to the most stable one,That is why you use ***add*** keyword in your command as it would try to keep the most stable 
version of dependency that would make the dependency usable of the current install Sdk version on your system.


In the Documentaion starting I mention to use flutter warning in order to debug the build or development issue in the project as it would make is easier for you to
make all the changes in either ***build.gradle*** or ***settings.gradle*** files

Here is the example of That:

```
Your project is configured to compile against Android SDK 33, but the following plugin(s) require to be compiled against a higher Android SDK version:
- cloud_firestore compiles against Android SDK 34
- device_info_plus compiles against Android SDK 34
- firebase_auth compiles against Android SDK 34
- firebase_core compiles against Android SDK 34
- firebase_storage compiles against Android SDK 34
- flutter_plugin_android_lifecycle compiles against Android SDK 34
- image_cropper compiles against Android SDK 34
- image_picker_android compiles against Android SDK 34
- open_file_android compiles against Android SDK 34
- path_provider_android compiles against Android SDK 34
- pdf_image_renderer compiles against Android SDK 35
- permission_handler_android compiles against Android SDK 34
- printing compiles against Android SDK 34
- share_plus compiles against Android SDK 34
- shared_preferences_android compiles against Android SDK 34
- sqflite_android compiles against Android SDK 34
- url_launcher_android compiles against Android SDK 34
Fix this issue by compiling against the highest Android SDK version (they are backward compatible).
Add the following to D:\project\Menu-Planner-App\android\app\build.gradle:

    android {
        compileSdk = 35
        ...
    }

Package open_file:macos references open_file_macos:macos as the default plugin, but the package does not exist, or is not a plugin package.
Ask the maintainers of open_file to either avoid referencing a default implementation via `platforms: macos: default_package: open_file_macos` or create a plugin named open_file_macos.

Font asset "MaterialIcons-Regular.otf" was tree-shaken, reducing it from 1645184 to 7836 bytes (99.5% reduction). Tree-shaking can be disabled by providing the --no-tree-shake-icons flag when building your app.

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':app:checkReleaseAarMetadata'.
> A failure occurred while executing com.android.build.gradle.internal.tasks.CheckAarMetadataWorkAction
   > 24 issues were found when checking AAR metadata:

       1.  Dependency 'androidx.credentials:credentials:1.2.0-rc01' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       2.  Dependency 'androidx.credentials:credentials-play-services-auth:1.2.0-rc01' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       3.  Dependency 'androidx.fragment:fragment-ktx:1.7.1' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       4.  Dependency 'androidx.activity:activity-ktx:1.9.3' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       5.  Dependency 'androidx.lifecycle:lifecycle-livedata:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       6.  Dependency 'androidx.lifecycle:lifecycle-livedata-core-ktx:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       7.  Dependency 'androidx.lifecycle:lifecycle-viewmodel-ktx:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       8.  Dependency 'androidx.lifecycle:lifecycle-runtime-ktx:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

       9.  Dependency 'androidx.lifecycle:lifecycle-livedata-core:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      10.  Dependency 'androidx.lifecycle:lifecycle-viewmodel-savedstate:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      11.  Dependency 'androidx.lifecycle:lifecycle-viewmodel:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      12.  Dependency 'androidx.lifecycle:lifecycle-runtime:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      13.  Dependency 'androidx.lifecycle:lifecycle-process:2.7.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      14.  Dependency 'androidx.window:window-java:1.2.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      15.  Dependency 'androidx.window:window:1.2.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      16.  Dependency 'androidx.datastore:datastore-core-android:1.1.1' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      17.  Dependency 'androidx.datastore:datastore-preferences-android:1.1.1' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      18.  Dependency 'androidx.datastore:datastore-android:1.1.1' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      19.  Dependency 'androidx.fragment:fragment:1.7.1' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      20.  Dependency 'androidx.activity:activity:1.9.3' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      21.  Dependency 'androidx.browser:browser:1.8.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      22.  Dependency 'androidx.core:core-ktx:1.13.1' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      23.  Dependency 'androidx.core:core:1.13.1' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

      24.  Dependency 'androidx.annotation:annotation-experimental:1.4.0' requires libraries and applications that
           depend on it to compile against version 34 or later of the
           Android APIs.

           :app is currently compiled against android-33.

           Also, the maximum recommended compile SDK version for Android Gradle
           plugin 8.1.0 is 33.

           Recommended action: Update this project's version of the Android Gradle
           plugin to one that supports 34, then update this project to use
           compileSdk of at least 34.

           Note that updating a library or application's compileSdk (which
           allows newer APIs to be used) can be done separately from updating
           targetSdk (which opts the app in to new runtime behavior) and
           minSdk (which determines which devices the app can be installed
           on).

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
> Get more help at https://help.gradle.org.

BUILD FAILED in 1m 38s
Running Gradle task 'assembleRelease'...                          100.4s
Gradle task assembleRelease failed with exit code 1
```
##Note

If you intend to maintain flutter application for a long time avoid using the third party dependecies you will be able
to resolve the any issue with android and flutter Sdk but pub dependecies you will never be able to resovle if the 
maintainer is not maintaining it.

## Links That Might Help

[https://stackoverflow.com/questions/43928702/how-to-change-the-application-launcher-icon-on-flutter]
[https://github.com/dart-lang/sdk/issues]
[https://github.com/DavBfr/dart_pdf/issues/1721]
[https://pub.dev/]

