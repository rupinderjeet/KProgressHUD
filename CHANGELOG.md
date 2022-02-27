# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- All Clear

## [1.0.0] - 2022-02-28
### Added
- Adds this CHANGELOG.md
- Adds Kotlin 1.6.10
- Adds setup for maven-publishing
- Adds `viewBinding` build feature for "demo" module
- Adds `androidx.core:core-ktx` to `1.7.1`

### Changed
- Changes gradle-wrapper from `4.4-all` to `7.2-bin`
- Changes `settings.gradle` to add `pluginManagement` & `dependencyResolutionManagement`
- Changes `minSdkVersion` to 21
- Changes `compileSdkVersion` to 31
- Changes `targetSdkVersion` to 31
- Changes `gradle.properties` to support `androidx` using `android.useAndroidX=true`
- Changes package name for "demo" module to `io.github.rupinderjeet.kprogresshud.demo`
- Changes package name for "kprogresshud" to `io.github.rupinderjeet.kprogresshud`
- Changes `androidx.appcompat:appcompat` dependency from support version to `1.4.1`
- Changes `versionCode` to `1` and `versionName` to `1.0.0`
- Changes README.md for latest information.

### Removed
- Removes test-implementations because there are no tests as of now
- Removes Build Version Code checks below `minSdkVersion`

## [Fork 1.2.0] - 2019-02-19
- Source Repository: https://github.com/Kaopiz/KProgressHUD
- Source Repository Developer: https://github.com/tuanna-hsp
- Forked from commit: 30ebaba6233879f6b645bb791562b6d8334a7314

[Unreleased]: https://github.com/rupinderjeet/KProgressHUD/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/rupinderjeet/KProgressHUD/compare/v0.0.1...v1.0.0
[Fork 1.2.0]: https://github.com/rupinderjeet/KProgressHUD/releases/tag/v0.0.1












