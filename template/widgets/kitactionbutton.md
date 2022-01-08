# KitActionButton

### Description

An action button which contains solid borders, and an icon in the center.

### Preview

![](<../../.gitbook/assets/Screenshot\_20211224-145413 - Copie - Copie.jpg>)

### Code

{% code title="action_button.dart" %}
```dart
class KitActionButton extends StatelessWidget {
  final IconData icon;
  final Color? fillColor;
  final Color? borderColor;
  final Color? iconColor;
  final Function() onPressed;
  
  const KitActionButton({Key? key,
    required this.icon,
    required this.onPressed,
    this.fillColor,
    this.iconColor,
    this.borderColor}) : super(key: key);
    ...
}
```
{% endcode %}

### API

| Property      | Description                                      | Type       | Default            |
| ------------- | ------------------------------------------------ | ---------- | ------------------ |
| `icon`        | The main icon of the button                      | IconData   | -                  |
| `fillColor`   | Background color                                 | Color      | False              |
| `borderColor` | Color of borders                                 | Color      | (Icon theme color) |
| `iconColor`   | Color of the icon                                | Color      | (Icon theme color) |
| `onPressed`   | Function to call when widget (button) is pressed | Function() | -                  |
