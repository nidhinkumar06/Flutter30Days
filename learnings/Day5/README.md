<div align="center">
  <h1>Flutter - Day 5</h1>
  <p>Infinite List view with Scrolling</p>
</div>

1. Create an flutter app using the command `flutter create application_name` or if you are using vs code editor the click `view->command palette` and then select `Flutter new project` Give the app name and click create

2. Once the application is created click `main.dart` file and remove all the existing codes

3. import the `material.dart` package which will have the material theme

4. Add the `main()` with `runApp()` like below

```
void main() => runApp(MyApp());

```

5. Create a stateless widget(Which is immutable cannot be changed) with name `MyApp()` like below

```
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Welcome to Flutter',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```
* The app extends to a StatelessWidget which makes the app itself a widget
* `Scaffold` is an widget from Material which provides the appBar, title and a body property which holds a widget tree for the homescreen


# Using External Package

To use an external package we can use the [pub.dev](https://pub.dev/) which is similar like npm where we take the necessary package and add it to `pubspec.yaml` file

For example we have taken an english_words which will have list of english words copy the package name and go to the `pubspec.yaml` file and do like below

```
@@ -5,4 +5,5 @@    
   dependencies:            
      flutter:            
        sdk: flutter            
        cupertino_icons: ^0.1.2            
+       english_words: ^3.1.0
```

In `lib/main.dart` file import the english_words package

```
import 'package:flutter/material.dart';
import 'package:english_words/english_words.dart';
```


# Adding Stateful widget

Stateful widget maintains state that might change during the lifetime of the widget. 

Implementing a Stateful widget requires 2 classes

1. Stateful widget creates an instance of the State class
2. The `StatefulWidget` class is, itself, immutable, but the State class persists over the lifetime of the widget.

```
class TestWidget extends StatefulWidget {
  @override
  _TestWidgetState createState() => _TestWidgetState();
}

class _TestWidgetState extends State<TestWidget> {
  @override
  Widget build(BuildContext context) {
    return Container(
      
    );
  }
}
```

# Infinite scroll

ListView builder

```
Widget _buildSuggestions() {
  return ListView.builder(
      padding: const EdgeInsets.all(16.0),
      itemBuilder: /*1*/ (context, i) {
        if (i.isOdd) return Divider(); /*2*/

        final index = i ~/ 2; /*3*/
        if (index >= _suggestions.length) {
          _suggestions.addAll(generateWordPairs().take(10)); /*4*/
        }
        return _buildRow(_suggestions[index]);
      });
}
```

_buildRow

```
Widget _buildRow(WordPair pair) {
  return ListTile(
    title: Text(
      pair.asPascalCase,
      style: _biggerFont,
    ),
  );
}
```


# Resource Link

[Click here to view the resource](https://flutter.dev/docs/get-started/codelab#step-1-create-the-starter-flutter-app)