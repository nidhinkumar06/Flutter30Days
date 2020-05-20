<div align="center">
  <h1>Flutter - Day 8</h1>
  <p>UserInterface - Gesture Detector</p>
</div>

Gesture detector doesn't have any visual representation but instead it detects gestures made by the user. Example when the user clicks the container, the gesture calls the onTap() callback.

Many widgets provides optional feedback to handle the gestures like the IconButton, RaisedButton etc.

```
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () {
        print('Button got clicked');
      },
      child: Container(
        height: 56.0,
        padding: EdgeInsets.all(8.0),
        margin: EdgeInsets.symmetric(horizontal: 8.0),
        decoration: BoxDecoration(
          borderRadius: BorderRadius.circular(5.0),
          color: Colors.blue,
        ),
        child: Center(
          child: Text('Button Gesture'),
        ),
      ),
    );
  }
}

```





