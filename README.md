# ARTOM Android Source Project

This project packages the existing ARTOM HTML/CSS/JavaScript app inside a small Android WebView app.
The ARTOM interface and its existing browser features are reused; this is not a Flutter rewrite.

## Included
- Existing ARTOM app: `app/src/main/assets/index.html`
- Android wrapper: `app/src/main/java/com/artom/studio/MainActivity.kt`
- Android manifest and Gradle build files
- GitHub Actions workflow to build an installable debug APK in the cloud

## Build a test APK using GitHub from your Android phone

1. Download and extract this ZIP on your phone, or upload the ZIP itself to a new GitHub repository.
   If GitHub's website does not let you upload a ZIP as a project, extract it first using your phone's Files app and upload the files/folders inside `ARTOM-Android-Source`.
2. Create a GitHub repository named `ARTOM-Android-Source`.
3. Upload the project contents, keeping the folder structure exactly as shown. Make sure `.github/workflows/build-android.yml` is included.
4. Open the repository's **Actions** tab.
5. Select **Build ARTOM Android APK** and tap **Run workflow**. A push to the `main` branch also starts a build.
6. When the run finishes successfully, open it and download the `ARTOM-debug-APK` artifact.
7. Extract the downloaded artifact ZIP and install `app-debug.apk` on your Android phone. Android may ask you to allow installation from your browser or file manager.

## Important notes
- The APK built by this workflow is a **debug/test APK**, suitable for installing and testing. It is not the signed release build for Google Play.
- For Google Play publishing, create a signed release build and an Android App Bundle (AAB), and configure app signing.
- This first Android wrapper keeps ARTOM's current local-browser storage behavior. Saved projects are stored locally in the app's WebView data; uninstalling or clearing app data can erase them.
- The current ARTOM HTML app does not yet include AI image generation, cloud accounts/sync, AdMob ads, or Flutterwave payments.
- The existing PNG export and image import are included. Device-specific behavior should be tested on the actual phone.
- The project uses Android Gradle Plugin 8.7.3, Gradle 8.9, JDK 17 and Android SDK 35.
