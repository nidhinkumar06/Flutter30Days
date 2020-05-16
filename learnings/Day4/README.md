<div align="center">
  <h1>Flutter - Day 4</h1>
  <p>Baking app  - Login page design</p>
</div>

# main.dart

```
import 'package:flutter/material.dart';
import 'package:quizapp/constants.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'AuthScreen1',
      theme: ThemeData(
        brightness: Brightness.dark,
        primaryColor: kPrimaryColor,
        scaffoldBackgroundColor: kBackgroundColor,
        textTheme: TextTheme(
          display1: TextStyle(color: Colors.white, fontWeight: FontWeight.bold),
          button: TextStyle(color: Colors.white),
          headline:
              TextStyle(color: Colors.white, fontWeight: FontWeight.normal),
        ),
      ),
      home: WelcomeScreen(),
    );
  }
}

class WelcomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Column(
        children: <Widget>[
          Expanded(
            flex: 3,
            child: Container(
              decoration: BoxDecoration(
                  image: DecorationImage(
                      image: AssetImage("assets/bake.jpeg"),
                      fit: BoxFit.cover)),
            ),
          ),
          Expanded(
            child: Column(
              children: <Widget>[
                RichText(
                  textAlign: TextAlign.center,
                  text: TextSpan(children: [
                    TextSpan(
                        text: "BAKING LESSONS\n",
                        style: Theme.of(context).textTheme.display1),
                    TextSpan(
                        text: "MASTER THE ART OF BAKING",
                        style: Theme.of(context).textTheme.headline)
                  ]),
                ),
                Container(
                  padding: EdgeInsets.symmetric(horizontal: 26, vertical: 16),
                  decoration: BoxDecoration(borderRadius: BorderRadius.circular(25),
                  color: kPrimaryColor,
                  ),
                ),
              ],
            ),
          )
        ],
      ),
    );
  }
}
```

# constants.dart

```
import 'package:flutter/material.dart';

const kBackgroundColor = Color(0xFF202020);
const kPrimaryColor = Color(0xFFFFBD73);
```

To Know what is 

1. Widget
2. ThemeData
3. Scaffold
4. BoxDecoration
5. DecorationImage
6. Expanded
7. RichText