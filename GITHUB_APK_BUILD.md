# Build the handset APK with GitHub Actions

The repository includes `.github/workflows/build-apk.yml`.

1. Push this project to a GitHub repository.
2. Open **Actions > Build Android APK**.
3. Choose **Run workflow**.
4. When the build succeeds, download the `Umniah-Network-Insights-debug-apk` artifact.
5. Install the APK on an Android handset after allowing installation from the browser/file manager used to open it.

The workflow uses JDK 17, Android SDK 37 and Gradle 9.6.1 and builds the `app` debug variant.

This is a development/test APK, not a production release-signed package. Production distribution requires an Umniah-controlled signing key and the production backend configuration.
