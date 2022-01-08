# KitShowError

### Description

An illustration with an error message to show when an error is occured.

### Preview

### Code

{% code title="show_error.dart" %}
```dart
class KitShowError extends StatelessWidget {
  final String message;
  final Function()? onTryAgain;
  final bool useTranslation;
  const KitShowError({required this.message,this.onTryAgain,this.useTranslation = true, Key? key}) : super(key: key);
...
}
```
{% endcode %}

### API

| Property         | Description                                                       | Type       | Default |
| ---------------- | ----------------------------------------------------------------- | ---------- | ------- |
| `message`        | The error message                                                 | String     | -       |
| `onTryAgain`     | A callback function to trigger when 'Try again' button is pressed | Function() | -       |
| `useTranslation` | Whether to translate the error message or not                     | bool       | true    |
