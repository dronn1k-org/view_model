# View Model Divider

View Model Divider is a Flutter package that provides a convenient way to manage view models and their lifecycle within your Flutter applications. This package includes a set of classes and utilities to streamline the integration of view models with your UI components.

## Installation

To use View Model Divider in your Flutter project, add the following dependency to your `pubspec.yaml` file:

```yaml
dependencies:
  view_model_divider: ^1.0.0
```

Then, run `flutter pub get` to install the package.

## Usage

View Model Divider simplifies the creation and management of view models in your Flutter application. Here's a brief overview of how to use it:

### Creating a View Model

To create a new view model, simply extend the `ViewModel` class provided by the package. You can override lifecycle methods such as `initState`, `didChangeDependencies`, `activate`, `deactivate`, `dispose`, and `reassemble` to handle various aspects of your view model's lifecycle.

```dart
import 'package:view_model_divider/view_model.dart';

class MyViewModel extends ViewModel {
  @override
  void initState() {
    // Initialize your view model
  }

  // Override other lifecycle methods as needed
}
```

### Integrating with UI Components

Once you've defined your view model, you can integrate it with your UI components using the `BaseView` widget provided by the package. Pass your view model instance to the `BaseView` widget and implement the `build` method to build your UI.

```dart
import 'package:view_model_divider/view.dart';

class MyWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return BaseView<MyViewModel>(
      vmFactory: (context) => MyViewModel(context),
      builder: (context, viewModel) {
        // Build your UI using the view model
      },
    );
  }
}
```

### Example

```dart
import 'package:flutter/material.dart';
import 'package:view_model_divider/view.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('View Model Divider Example'),
        ),
        body: Center(
          child: BaseView<MyViewModel>(
            vmFactory: (context) => MyViewModel(context),
            builder: (context, viewModel) {
              // Build your UI using the view model
            },
          ),
        ),
      ),
    );
  }
}

class MyViewModel extends ViewModel {
  @override
  void initState() {
    // Initialize your view model
  }

  // Override other lifecycle methods as needed
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Flutter Team: For creating an amazing framework.
- Open-source community: For valuable contributions and feedback.

## Support

For any questions or issues, please [open an issue](https://github.com/example/view_model_divider/issues) on GitHub.

---
**Note:** This package is a simplified version for demonstration purposes. For a comprehensive view model solution, consider using other packages or implementing additional features as needed.
