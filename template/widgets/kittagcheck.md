# KitTagCheck

### Description

A selectable tag with a label.

### Preview

![](<../../.gitbook/assets/Screenshot\_20211224-145457 - Copie.jpg>)

### Code

{% code title="tag_check.dart" %}
```dart
class KitTagCheck extends StatefulWidget {

  final String label;
  bool isChecked;
  final Function(bool checked) onChange;

  KitTagCheck({required this.label, required this.onChange, this.isChecked = false, Key? key}) : super(key: key);

  ...
}
```
{% endcode %}

### API

| Property    | Description                                 | Type           | Default |
| ----------- | ------------------------------------------- | -------------- | ------- |
| `label`     | The label shown on the tag                  | String         | -       |
| `isChecked` | Is the item checked (selected)              | String         | -       |
| `onChange`  | Callback when the selected item has changed | Function(bool) | -       |
