Build: open this folder in Android Studio, let it sync, then Build > Build APK(s).
If Gradle cannot download de.robv.android.xposed:api:82 (api.xposed.info is sometimes down),
download XposedBridgeAPI-82.jar, put it in app/libs/ and in app/build.gradle.kts replace the
compileOnly line with: compileOnly(files("libs/XposedBridgeAPI-82.jar"))

Install the APK, enable it in LSPosed (scope: System UI), then run:
  adb shell "su -c 'killall com.android.systemui'"
Check LSPosed manager > Logs > Modules for the "NoSwipeHaptics:" lines.

No Android Studio? Upload this folder's contents to a GitHub repo (including the .github folder).
The Actions tab > "Build APK" > Run workflow builds app-debug.apk for you (artifact: NoSwipeHaptics-apk).
