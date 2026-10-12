# Umniah Network Insights

Premium-dark Android telecom intelligence client: simple customer UX on top of a permission-aware, battery-conscious telemetry probe.

## What is included
- Kotlin + Jetpack Compose + Material 3
- Hilt, Coroutines/Flow, Room, DataStore, WorkManager
- Device, subscription, cellular/RAN, 4G/5G, carrier-privileged IMS extension, Wi-Fi and connectivity collectors
- Consent-aware location and mobility proxy
- DNS/TCP/TLS/HTTP and bounded performance diagnostics
- Experience scoring, event detection and evidence-first diagnostics
- Encrypted offline telemetry queue and batch-upload worker
- Premium dark Umniah design system using the supplied brand artwork
- Home, diagnostics, network details, timeline, map integration point, Privacy Center, Settings and AI Network Analyst
- OpenAPI, PostgreSQL and ClickHouse backend contracts
- Unit tests and production test/deployment runbooks

## Build baseline
- minSdk 26
- target/compile SDK 37
- Android Gradle Plugin 9.4.0
- Gradle 9.6
- Kotlin 2.4.20
- Compose BOM 2026.09.00
- Material 3 stable channel

## Important safe defaults
Telemetry uploads are disabled until a real governed backend is configured. Background precise location is not requested by the consumer baseline. Permanent subscriber/device identifiers are not collected. Missing Android/OEM measurements remain unavailable rather than being synthesized.

## Start
Open the root folder in Android Studio, install API 37/JDK 17, sync Gradle, and run the `app` module. Review `docs/PHASES.md` and `docs/DEPLOYMENT.md` before turning on production telemetry upload.
