<div align="center">
  <h1>Flutter - Day 6</h1>
  <p>UserInterface - Intro to Widgets</p>
</div>

# Basic widgets

* Text
* Row (Horizontal View)
* Column (Vertical view)
* Stack
* Container


Sample widget with toolbar and container like below which has two stateless widgets namely 

* MyScaffold()
* MyAppBar()

```
void main() => runApp(
  MaterialApp(
    title: 'My app',
    home: MyScaffold(),
  ),
);

class MyScaffold extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Material(
      child: Column(
        children: <Widget>[
          MyAppBar(
            title: Text(
              'Example Title',
              style: Theme.of(context).primaryTextTheme.display1,
            ),
          ),
          Expanded(
            child: Center(
              child: Text('Hello world'),
            ),
          ),
        ],
      ),
    );
  }
}

class MyAppBar extends StatelessWidget {
  MyAppBar({this.title});


  final Widget title;

  @override
  Widget build(BuildContext context) {
    return Container(
      height: 56.0,
      padding: EdgeInsets.symmetric(horizontal: 8.0),
      decoration: BoxDecoration(color: Colors.blue[500]),
      child: Row(
        children: <Widget>[
          IconButton(
            icon: Icon(Icons.menu),
            tooltip: 'Navigation menu',
            onPressed: null,
          ),
          Expanded(
            child: title,
          ),
          IconButton(
            icon: Icon(Icons.search),
            tooltip: 'Search',
            onPressed: null,
          ),
        ],
      ),
    );
  }
}
```

* Expanded - expands to fill any remaining available space that hasn’t been consumed by the other children.
* Navigator - which manages a stack of widgets identified by strings, also known as “routes”. Transistion between screens smoothly