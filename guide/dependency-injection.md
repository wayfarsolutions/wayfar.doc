# Dependency Injection

### Service locator

To be able to register dependencies and use them widely in the app, we use the [**get\_it**](https://pub.dev/packages/get\_it) package which is a service locator for Flutter projects.

It offers many possibilities to register objects: singletons, factories,..., see the example below:

```dart
sl.registerLazySingleton(()=> Storage());
sl.registerLazySingleton(() => ThemeBloc());
```

{% hint style="info" %}
Note that `sl` is a global variable, located in the file `lib/src/core/di/locator.dart`
{% endhint %}

### Configuring features

When you add a new feature you can use register the corresponding dependencies by using the class `Feature` :

![](<../.gitbook/assets/Capture2 (1).PNG>)

After overriding required methods and registering the necessary objects, head over to `main.dart` under the folder `lib/src/core` and configure the feature by calling the `init()` method :

{% code title="main.dart" %}
```dart
/// Initialize the app, by initializing all the app features
///
init() { 
  _registerCoreDependencies();
  AuthFeature.init();
  ...
  BookmarksFeature.init();
  HomeFeature.init();
  // Add new feature here
}
```
{% endcode %}

{% hint style="warning" %}
The order of instructions is important in the init function since we can have interdependent features.
{% endhint %}
