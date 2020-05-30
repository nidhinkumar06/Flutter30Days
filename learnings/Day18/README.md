<div align="center">
  <h1>Flutter - Day 18</h1>
  <p>UserInterface - Navigation</p>
</div>

To push/move from one route to another we will use `Navigator.push` and to go back from one screen back to the previous screen we would use `Navigator.pop`

# Navigator.push

```
onPressed: () {
  Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => SecondRoute()),
  );
}
```

# Navigator.pop

```
onPressed: () {
  Navigator.pop(context);
}
```

# Navigate with named routes

If you need to navigate to the same screen in different parts of the app then we would use `Navigator.pushNamed()`

In the root application we will define the roots like below

```
MaterialApp(
  // Start the app with the "/" named route. In this case, the app starts
  // on the FirstScreen widget.
  initialRoute: '/',
  routes: {
    // When navigating to the "/" route, build the FirstScreen widget.
    '/': (context) => FirstScreen(),
    // When navigating to the "/second" route, build the SecondScreen widget.
    '/second': (context) => SecondScreen(),
  },
);
```

#### Navigating to the second screen

```
// Within the `FirstScreen` widget
onPressed: () {
  // Navigate to the second screen using a named route.
  Navigator.pushNamed(context, '/second');
}
```

#### Navigate to previous screen

```
// Within the SecondScreen widget
onPressed: () {
  // Navigate back to the first screen by popping the current route
  // off the stack.
  Navigator.pop(context);
}
```