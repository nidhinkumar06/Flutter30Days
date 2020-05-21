<div align="center">
  <h1>Flutter - Day 9</h1>
  <p>UserInterface - Changing widgets in response to input</p>
</div>

Using Stateful widget how we are getting the response to a input

we will create an simple counter stateful widget which will increment the number when we click the button

```
import 'package:flutter/material.dart';
import 'package:flutter/widgets.dart';

void main() => runApp(Counter());



class Counter extends StatefulWidget {
  @override
  _CounterState createState() => _CounterState();
}

class _CounterState extends State<Counter> {
  int _counter = 0;

  void _increment() {
    setState(() {
      _counter++;
    });
  }


  @override
  Widget build(BuildContext context) {
    return Row(
      children: <Widget>[
        RaisedButton(
          onPressed: _increment,
          child: Text('Increment'),
        ),
        Text('Count: $_counter')
      ],
    );
  }
}
```

Whenever the button is clicked it will call the `_increment` function which is available in the CounterState

# What is Stateful Widget

StatefulWidgets are special widgets that know how to generate State objects, which are then used to hold state.