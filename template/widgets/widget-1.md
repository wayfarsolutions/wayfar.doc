# KitAppBar

### Description

The application top bar that contains a title, main button and menu options.

### Preview

![](<../../.gitbook/assets/Screenshot\_20211224-145413 - Copie.jpg>) ![](<../../.gitbook/assets/Screenshot\_20211224-145625 - Copie.jpg>)

### Code

{% code title="app_bar.dart" %}
```dart
class KitAppBar extends StatelessWidget implements PreferredSizeWidget {
 
  KitAppBar._({Key? key}) : super(key: key);

  KitAppBar.simple(this._title,  {this.transparent = false, this.actions, Key? key}): super(key: key);

  KitAppBar.withUpButton(this._title, {this.transparent = false, this.actions, Key? key}): super(key: key) {
  }

  KitAppBar.withDrawerButton(this._title, {this.transparent = false, this.actions, Key? key}): super(key: key) {}
  }
}
```
{% endcode %}

### API

| Property      | Description                                                                        | Type          | Default |
| ------------- | ---------------------------------------------------------------------------------- | ------------- | ------- |
| `title`       | The title in the app bar                                                           | String        | -       |
| `transparent` | Is the background of the app bar transparent                                       | Boolean       | False   |
| `actions`     | Widgets to show on the right of the app bar                                        | List\<Widget> | -       |
| `leading`     | The widget (one) to show on the left of the app bar (Back button or Drawer button) | Widget        |         |
