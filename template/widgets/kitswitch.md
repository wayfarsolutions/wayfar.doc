# KitSwitch

### Description

A switch widget that can select between multiple options.

### Preview

![](<../../.gitbook/assets/Screenshot\_20211224-145640 (2).jpg>)

### Code

{% code title="switch.dart" %}
```dart
class KitSwitch extends StatefulWidget {
  final Map<String, String> options;
  String? selected;
  double itemWidth;
  final Function(String key, String value) onChange;

  KitSwitch({required this.options, required this.onChange, this.selected = null, this.itemWidth = 100, Key? key}) : super(key: key);
  ....
}
```
{% endcode %}

### API

| Property    | Description                                          | Type                     | Default |
| ----------- | ---------------------------------------------------- | ------------------------ | ------- |
| `options`   | List of options represented by key-value pairs (Map) | Map\<String,String>      | -       |
| `selected`  | Selected key                                         | String                   | -       |
| `onChange`  | Callback when the selected item has changed          | Function(String, String) | -       |
| `itemWidth` | Width value of one item                              | double                   | -       |



