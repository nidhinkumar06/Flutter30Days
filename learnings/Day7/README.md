<div align="center">
  <h1>Flutter - Day 7</h1>
  <p>UserInterface - Material Widgets</p>
</div>

Instead of creating the appbar and custom widgets we can use the Material Widget which is available

```
import 'package:flutter/material.dart';

void main() => runApp(MaterialApp(
  title: 'FlutterExample',
  home: MaterialHome()
));

class MaterialHome extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: IconButton(
          icon: Icon(Icons.arrow_back),
          tooltip: 'Back',
          onPressed: null,
        ),
        title: Text('Hello Material'),
        actions: <Widget>[
          IconButton(
            icon: Icon(Icons.search),
            tooltip: 'Search',
            onPressed: null,
          )
        ],
      ),
      body: Center(
        child: Text('Hello Material body'),
      ),
      floatingActionButton: FloatingActionButton(
        tooltip: 'add',
        child: Icon(Icons.add),
        onPressed: null,
      ),
    );
  }
}
```

`leading` - A widget to display before the title.
