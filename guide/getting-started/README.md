# Getting Started

## Requirements

Before getting started, please be sure that you have these requirements installed :

* [Flutter](https://docs.flutter.dev/get-started/install)
* [Android Studio (for Windows)](https://developer.android.com/studio)
* [XCode (for Mac)](https://developer.apple.com/xcode/)

Once you setup the environment, open the project with the code editor that you like.

## Configuration

To run the app you have to configure some settings first, for the platform in which you like to run the app (**Android / iOS)** and register the app in **Firebase** console (See the links bellow).

{% content-ref url="android.md" %}
[android.md](android.md)
{% endcontent-ref %}

{% content-ref url="ios.md" %}
[ios.md](ios.md)
{% endcontent-ref %}

{% content-ref url="firebase.md" %}
[firebase.md](firebase.md)
{% endcontent-ref %}

## Build

#### For Android

To generate an APK file, run the following command in the root project folder :

```
flutter build android
```

Or, to generate an app bundle for Play Store release, run this:

```
flutter build appbundle
```

#### For iOS

