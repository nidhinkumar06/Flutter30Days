<div align="center">
  <h1>Flutter - Day 14</h1>
  <p>UserInterface - ScreenOrientation-Example</p>
</div>

We will created a simple flutter application which will fit based on the screen. i.e. If the screen width is lesser than 600 we will show a list view and then on the click of list view we will navigate to a new page that is detail page.
Suppose if the width > 600 means then we will show the master and detail page in a single screen that is the the selected list item will be displayed in the same screen


# How it is identified

We will use the `OrientationBuilder` and `MediaQuery` and based on the screen width we will display the screen

for that we will first create the below widgets

* ListWidget
* DetailWidget

Once these widgets are created we will create the `DetailPage` and `MasterDetailPage`

### Detail Widget

```
import 'package:flutter/material.dart';

class DetailWidget extends StatefulWidget {
  final int data;

  DetailWidget(this.data);

  @override
  _DetailWidgetState createState() => _DetailWidgetState();
}

class _DetailWidgetState extends State<DetailWidget> {
  @override
  Widget build(BuildContext context) {
    return Container(
      color: Colors.blue,
      child: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(widget.data.toString(),
                style: TextStyle(fontSize: 36.0, color: Colors.white))
          ],
        ),
      ),
    );
  }
}

```

### ListWidget

```
import 'package:flutter/material.dart';

typedef Null ItemSelectedCallback(int value);

class ListWidget extends StatefulWidget {
  final int count;
  final ItemSelectedCallback onItemSelected;

  ListWidget(
    this.count,
    this.onItemSelected,
  );

  @override
  _ListWidgetState createState() => _ListWidgetState();
}

class _ListWidgetState extends State<ListWidget> {
  @override
  Widget build(BuildContext context) {
    return ListView.builder(
      itemCount: widget.count,
      itemBuilder: (context, position) {
        return Padding(
          padding: const EdgeInsets.all(8.0),
          child: Card(
            child: InkWell(
              onTap: () {
                widget.onItemSelected(position);
              },
              child: Row(
                children: [
                  Padding(
                    padding: EdgeInsets.all(8.0),
                    child: Text(
                      position.toString(),
                      style: TextStyle(fontSize: 22),
                    ),
                  )
                ],
              ),
            ),
          ),
        );
      },
    );
  }
}

```

### DetailPage

```
import 'package:flutter/material.dart';
import 'package:multiplescreen_orientation/components/DetailWidget.dart';


class DetailPage extends StatefulWidget {
  final int data;

  DetailPage(this.data);

  @override
  _DetailPageState createState() => _DetailPageState();
}

class _DetailPageState extends State<DetailPage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(),
      body: DetailWidget(widget.data),
    );
  }
}
```

### MasterDetailPage

```
import 'package:flutter/material.dart';
import 'package:multiplescreen_orientation/DetailPage.dart';
import 'package:multiplescreen_orientation/components/DetailWidget.dart';
import 'package:multiplescreen_orientation/components/ListWidget.dart';

class MasterDetailPage extends StatefulWidget {
  @override
  _MasterDetailPageState createState() => _MasterDetailPageState();
}

class _MasterDetailPageState extends State<MasterDetailPage> {
  var selectedValue = 0;
  var isLargeScreen = false;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(),
      body: OrientationBuilder(
        builder: (context, orientation) {
          if (MediaQuery.of(context).size.width > 600) {
            isLargeScreen = true;
          } else {
            isLargeScreen = false;
          }

          return Row(
            children: [
              Expanded(
                child: ListWidget(10, (value) {
                  if (isLargeScreen) {
                    selectedValue = value;
                    setState(() {});
                  } else {
                    Navigator.push(context,
                        MaterialPageRoute(builder: (context) {
                      return DetailPage(value);
                    }));
                  }
                }),
              ),
              isLargeScreen
                  ? Expanded(
                      child: DetailWidget(selectedValue),
                    )
                  : Container(),
            ],
          );
        },
      ),
    );
  }
}

```

### main.dart

```
import 'package:flutter/material.dart';
import 'package:multiplescreen_orientation/MasterDetailPage.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: MasterDetailPage()
    );
  }
}
```