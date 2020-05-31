<div align="center">
  <h1>Flutter - Day 19</h1>
  <p>UserInterface - Pass arguments to a named directory</p>
</div>

To read the arguments using `ModelRoute.of()` and `onGenerateRoute()` using the steps

1. Define the arguments you need to pass.
2. Create a widget that extracts the arguments.
3. Register the widget in the routes table.
4. Navigate to the widget.

# Defining the arguments

```
// You can pass any object to the arguments parameter.
// In this example, create a class that contains a customizable
// title and message.
class ScreenArguments {
  final String title;
  final String message;

  ScreenArguments(this.title, this.message);
}
```

# Widget that extracts the arguments

```
// A widget that extracts the necessary arguments from the ModalRoute.
class ExtractArgumentsScreen extends StatelessWidget {
  static const routeName = '/extractArguments';

  @override
  Widget build(BuildContext context) {
    // Extract the arguments from the current ModalRoute settings and cast
    // them as ScreenArguments.
    final ScreenArguments args = ModalRoute.of(context).settings.arguments;

    return Scaffold(
      appBar: AppBar(
        title: Text(args.title),
      ),
      body: Center(
        child: Text(args.message),
      ),
    );
  }
}
```

# Register the routes in the route Table

```
MaterialApp(
  routes: {
    ExtractArgumentsScreen.routeName: (context) => ExtractArgumentsScreen(),
  },
);
```

# Navigate to the widget

```
// A button that navigates to a named route. The named route
// extracts the arguments by itself.
RaisedButton(
  child: Text("Navigate to screen that extracts arguments"),
  onPressed: () {
    // When the user taps the button, navigate to a named route
    // and provide the arguments as an optional parameter.
    Navigator.pushNamed(
      context,
      ExtractArgumentsScreen.routeName,
      arguments: ScreenArguments(
        'Extract Arguments Screen',
        'This message is extracted in the build method.',
      ),
    );
  },
),
```

Alternatively using `onGenerateRoute()` we can extract the arguments

```
MaterialApp(
  // Provide a function to handle named routes. Use this function to
  // identify the named route being pushed, and create the correct
  // screen.
  onGenerateRoute: (settings) {
    // If you push the PassArguments route
    if (settings.name == PassArgumentsScreen.routeName) {
      // Cast the arguments to the correct type: ScreenArguments.
      final ScreenArguments args = settings.arguments;

      // Then, extract the required data from the arguments and
      // pass the data to the correct screen.
      return MaterialPageRoute(
        builder: (context) {
          return PassArgumentsScreen(
            title: args.title,
            message: args.message,
          );
        },
      );
    }
  },
);
```