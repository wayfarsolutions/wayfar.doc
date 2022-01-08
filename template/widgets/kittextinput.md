# KitTextInput

### Description

Custom decorated text input based on Material **TextFormField.**

### Preview

![](<../../.gitbook/assets/Screenshot\_20211224-145341 - Copie.jpg>)

### Code

{% code title="text_input.dart" %}
```dart
class KitTextInput extends StatelessWidget {
  final String? initialValue;
  final String? placeholder;
  final bool obscureText;
  final FormFieldValidator<String>? validator;
  final Widget? prefixIcon;
  final Widget? suffixIcon;
  final Function(String? value)? onValueChange;
  final TextEditingController? controller;
  final Function(String? value)? onSaved;
  final TextInputType? keyboardType;
  final bool? enabled;
  final Function(String? value)? onSubmitted;
  final FocusNode? focusNode;
    final TextInputAction? textInputAction;
    final int? maxLines;

  const KitTextInput({
  ...})
  }
```
{% endcode %}

### API

This widget has the same properties of **TextFormField**, please refer to official documentation:&#x20;

{% embed url="https://api.flutter.dev/flutter/material/TextFormField-class.html" %}
