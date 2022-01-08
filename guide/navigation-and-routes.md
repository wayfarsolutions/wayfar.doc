# Navigation and routes

## Routing

When you add a new screen, you have to register it in `ROUTES` static class, in the file `lib/core/navigation/routes.dart` :

{% code title="routes.dart" %}
```dart
class ROUTES {
  static final String Home = "/";
  static final String Example = "/example";
  ...
}
```
{% endcode %}

Now map it to the corresponding widget (screen) using the `registerRoutes` function :

{% code title="routes.dart" %}
```dart
Map<String, WidgetBuilder> registerRoutes() {
  return <String, WidgetBuilder>{
    ROUTES.Home: (context) => AuthGuard(context, Home()),
    ROUTES.Examle: (context) => ExampleScreen(),
    ...
    };
}
```
{% endcode %}

If the screen needs arguments, use the function `onGenerateAppRoute` to pass parameters to the screen :&#x20;

{% code title="routes.dart" %}
```dart
Route onGenerateAppRoute(RouteSettings settings) {
  var route = settings.name;
  if (route==ROUTES.ParkingDetails) {
    // Read arguments from RouteSettings
    RouteArgs<String> args = settings.arguments as RouteArgs<String>;
    return MaterialPageRoute(
      builder: (context) {
        return AuthGuard(context, ParkingDetailScreen(
          parkingId: args.value,
        ));
      },
    );
  }

```
{% endcode %}

## Protecting routes

To protect routes from unauthorized access, an authentication guard has been implemented (`AuthGuard`).&#x20;

If the user is not authenticated, the guard redirect it to the sign in screen, otherwise the access is granted :

{% code title="auth_guard.dart" %}
```dart
Widget AuthGuard(BuildContext context, Widget widget) {
  return BlocBuilder<AuthenticationBloc, AuthenticationState>(
    bloc: resolve<AuthenticationBloc>(),
    builder: (BuildContext context, state) {
      if (state is Uninitialized) return Scaffold(body: Container());
      return (state is Authenticated) ? widget : SignInScreen();
    },
  );
}
```
{% endcode %}

## Drawer menu

To be able to add or edit items form the application drawer menu, head over to the file `menu.dart` under `lib/core/navigation`.

You can add a record by giving it a **key**, an **icon** and the corresponding [**route**](navigation-and-routes.md#routing) :

{% code title="menu.dart" %}
```dart
final menu = [
  {
    "key": "home",
    "icon": FontAwesomeIcons.home,
    "route": ROUTES.Home,
  },
  ...
]
```
{% endcode %}
