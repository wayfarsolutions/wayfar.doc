# Android

## App configuration

### Application ID

It is recommended to change the application ID to be sure that you have a unique identifier. Open the file <mark style="background-color:blue;">**`build.gradle`**</mark> located in <mark style="background-color:blue;">`android/app`</mark> and update the "_applicationId"_ property in the "_defaultConfig"_ section

The convention for application id is to hold this format: `com.<Organization>.<Product>`

{% code title="" %}
```groovy
defaultConfig {
        // TODO: Specify your own unique Application ID (https://developer.android.com/studio/build/application-id.html).
        applicationId "myparking.example.my_parking_v2"
        minSdkVersion 21
        targetSdkVersion 30
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
    }
```
{% endcode %}

### Package name

By default the package name should match the application id, so it's recommended to update it accordingly. Open the file **`AndroidManifest.xml`** located in `android/app/src/main` and update the "_package_" attribute of the root element.

{% code title="AndroidManifest.xml" %}
```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    package="myparking.example.my_parking_v2">
    ...
</manifest>
```
{% endcode %}

## Signing the app <a href="#signing-the-app" id="signing-the-app"></a>

{% hint style="info" %}
This step is **optional** for running and testing the app, it is needed once you want to publish the app and you want to generate a release build.
{% endhint %}

### Create a keystore

To create a keystore, run the following command (Replace \[alias\_name] by a name of your choice)

```bash
keytool -genkey -v -keystore keystore.jks -alias [alias_name] -keyalg RSA -keysize 2048 -validity 10000
```

After creating a keystore, create a new file **`key.properties`** inside `android` folder, that contains a reference to your keystore:

{% code title="key.properties" %}
```
storePassword=<password from previous step>
keyPassword=<password from previous step>
keyAlias=upload
storeFile=<location of the key store file>
```
{% endcode %}

### Configure signing in gradle

Edit the file `build.gradle` in order to use the created keystore:

1. Add the keystore information from your properties file before the `android` block:

{% code title="build.gradle" %}
```groovy
def keystoreProperties = new Properties()
   def keystorePropertiesFile = rootProject.file('key.properties')
   if (keystorePropertiesFile.exists()) {
       keystoreProperties.load(new FileInputStream(keystorePropertiesFile))
   }
```
{% endcode %}

2\. Find the `buildTypes` block, and edit is as the following:&#x20;

{% code title="build.gradle" %}
```groovy
    signingConfigs {
       release {
           keyAlias keystoreProperties['keyAlias']
           keyPassword keystoreProperties['keyPassword']
           storeFile keystoreProperties['storeFile'] ? file(keystoreProperties['storeFile']) : null
           storePassword keystoreProperties['storePassword']
       }
   }
   buildTypes {
       release {
           signingConfig signingConfigs.release
       }
   }
```
{% endcode %}

