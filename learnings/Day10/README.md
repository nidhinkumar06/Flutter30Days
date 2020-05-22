<div align="center">
  <h1>Flutter - Day 10</h1>
  <p>UserInterface - Creating Stateless widgets</p>
</div>

Today we will create a stateless widget which will have some dog names and we will move the repeated codes to a common one

So will create a statless widget which will have `MaterialApp` and `Scaffold` the datas

```
import 'package:flutter/material.dart';

void main() => runApp(BrunoApp());


class BrunoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Bruno Example',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Bruno Example'),
        ),
        body: Center(
          child: Text('Rocky'),
        ),
      ),
    );
  }
}
```

Now the above code will show the text at center named `Rocky`. Now we will add an decorated box like below

```
class BrunoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Bruno Example',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Bruno Example'),
        ),
        body: Center(
          child: DecoratedBox(
            child: Text('Rocky'),
            decoration: BoxDecoration(color: Colors.amberAccent),
          ),
        ),
      ),
    );
  }
}
```
Now we will add padding to the box like below code

```
class BrunoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Bruno Example',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Bruno Example'),
        ),
        body: Center(
          child: DecoratedBox(
            child: Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Rocky'),
            ),
            decoration: BoxDecoration(color: Colors.amberAccent),
          ),
        ),
      ),
    );
  }
}
```

Now we will wrap the `DecoratedBox` with `Column` like below code

```
class BrunoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Bruno Example',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Bruno Example'),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              DecoratedBox(
                child: Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: Text('Rocky'),
                ),
                decoration: BoxDecoration(color: Colors.amberAccent),
              ),
              DecoratedBox(
                child: Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: Text('Rocky'),
                ),
                decoration: BoxDecoration(color: Colors.amberAccent),
              ),
              DecoratedBox(
                child: Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: Text('Rocky'),
                ),
                decoration: BoxDecoration(color: Colors.amberAccent),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

Now we have repeated code of the DecoratedBox by creating a seperate stateless widget like below

```
class BrunoName extends StatelessWidget {
  final String name;

  BrunoName(this.name);
  @override
  Widget build(BuildContext context) {
    return DecoratedBox(
      child: Padding(
        padding: const EdgeInsets.all(8.0),
        child: Text(name),
      ),
      decoration: BoxDecoration(color: Colors.amberAccent),
    );
  }
}
```

Now we will remove the repeated code 

```
class BrunoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Bruno Example',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Bruno Example'),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              BrunoName('Rockey'),
              BrunoName('Rockey1'),
              BrunoName('Rockey2'),
            ],
          ),
        ),
      ),
    );
  }
}
```

Now the repeated code is removed and now the stateless widget is made simpler

Entire code

```
import 'package:flutter/material.dart';

void main() => runApp(BrunoApp());


class BrunoApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Bruno Example',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Bruno Example'),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              BrunoName('Rockey'),
              BrunoName('Rockey1'),
              BrunoName('Rockey2'),
            ],
          ),
        ),
      ),
    );
  }
}

class BrunoName extends StatelessWidget {
  final String name;

  BrunoName(this.name);
  @override
  Widget build(BuildContext context) {
    return DecoratedBox(
      child: Padding(
        padding: const EdgeInsets.all(8.0),
        child: Text(name),
      ),
      decoration: BoxDecoration(color: Colors.amberAccent),
    );
  }
}
```