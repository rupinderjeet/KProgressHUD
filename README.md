# KProgressHUD
[![Apache License](https://img.shields.io/badge/license-Apache-blue.svg)](http://opensource.org/licenses/Apache-2.0)

A progress HUD implementation for Android.
Inspired by [MBProgressHUD](https://github.com/jdg/MBProgressHUD) for iOS.

Originally developed at [Kaopiz/KProgressHUD](https://github.com/Kaopiz/KProgressHUD).
I forked this project since it was abandoned from almost 3 years. My intention is to update it for today's development & to republish it to `mavenCentral` since JCenter has shut down.

See [CHANGELOG](CHANGELOG.md) to see a list of changes I have made.

<img src="https://raw.githubusercontent.com/rupinderjeet/KProgressHUD/master/demo/screenshots/screencast.gif" width="200" />

## Compatibility

API 21 and later

## Adding KProgressHUD to your project

### Gradle
Add following to top of `settings.gradle` or update the existing code to add `mavenCentral()`:

```
pluginManagement {
    repositories {
        gradlePluginPortal()
        google()
        mavenCentral()
    }
}
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}
```
Include this in your app's `build.gradle`

```
implementation "io.github.rupinderjeet:kprogresshud:1.0.0"
```
Note that the package name has changed to `io.github.rupinderjeet.kprogresshud` now.

### Source code
If you want more control over the implementation, download and import the `kprogresshud` folder as a module to your project and modify according to your need.

## Usage

The usage of KProgressHUD is pretty straight forward. 
- Create the HUD, customize its style and show on the UI thread. 
- Fire a background worker to handle long-running tasks. 
- When done, call `dismiss()` to close (or if you use a determinate style, the HUD will automatically dismiss when progress reaches its maximum value).

Indeterminate HUD
```java
KProgressHUD hud = KProgressHUD.create(context)
	.setStyle(KProgressHUD.Style.SPIN_INDETERMINATE)
	.setLabel("Please wait")
	.setDetailsLabel("Downloading data")
	.setCancellable(true)
	.setAnimationSpeed(2)
	.setDimAmount(0.5f)
	.show();
```

Determinate HUD
```java
KProgressHUD hud = KProgressHUD.create(context)
    .setStyle(KProgressHUD.Style.ANNULAR_DETERMINATE)
    .setLabel("Please wait")
    .setMaxProgress(100)
    .show();
hud.setProgress(90);
```

You can also create a custom view to be displayed.
```java
ImageView imageView = new ImageView(context);
imageView.setBackgroundResource(R.drawable.spin_animation);
AnimationDrawable drawable = (AnimationDrawable) imageView.getBackground();
drawable.start();
KProgressHUD.create(context)
   .setCustomView(imageView)
   .setLabel("This is a custom view")
   .show();
```
Optionally, the custom view can implement `Determinate` or `Indeterminate` interface, which makes the HUD treat this view like the default determinate or indeterminate one.

See [**sample**](https://github.com/rupinderjeet/KProgressHUD/tree/master/demo/src/main) for more information.
<!--
TODO: See [**javadocs**](http://kaopiz.github.io/KProgressHUD/)
-->

## Contributing
1. Create a [Fork](https://github.com/rupinderjeet/KProgressHUD/fork)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'adds some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request on Github

## License [This Fork]
```
   Copyright 2022 Rupinderjeet Singh Hans
   Copyright 2015 Kaopiz Software Co., Ltd.

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
