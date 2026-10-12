# Umniah Network Insights - Android SDK Source Package

## Package purpose

This source package contains the premium-dark Umniah Network Insights Android client and its telecom telemetry modules. It can be used in two ways:

1. **Standalone handset application** - build the `app` module to produce an APK.
2. **Reusable telecom SDK source** - integrate the telemetry/domain/core modules into another Umniah Android application.

## Main modules

- `app` - premium-dark Jetpack Compose handset application
- `telemetry` - device, SIM, cellular/RAN, 4G/5G, Wi-Fi, connectivity, location and network-performance collection
- `domain` - event detection, diagnostics, experience scoring and mobility logic
- `core:model` - normalized telecom/domain models
- `core:data` - Room, encryption, repositories, API client and upload queue
- `core:designsystem` - Umniah premium-dark Compose theme and reusable UI components
- `backend` - OpenAPI plus PostgreSQL and ClickHouse contracts

## Build baseline

- minSdk 26
- targetSdk 37
- compileSdk 37
- Android Gradle Plugin 9.4.0
- Gradle 9.6
- JDK 17
- Kotlin 2.4.20

## Before production use

Configure and validate the real Umniah API gateway/authentication, telemetry retention policy, map provider, approved speed-test endpoints, certificate strategy, privacy/legal notices, carrier-privileged IMS behavior and device/OEM field-test matrix.

See `HANDSET_INSTALL.md`, `docs/DEPLOYMENT.md`, `docs/ANDROID_API_PERMISSION_MATRIX.md`, `docs/SECURITY_THREAT_MODEL.md`, and `docs/TEST_STRATEGY.md`.
