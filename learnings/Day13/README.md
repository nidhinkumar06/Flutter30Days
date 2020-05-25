<div align="center">
  <h1>Flutter - Day 13</h1>
  <p>UserInterface - Responsive Design</p>
</div>


How the screen should look in a laptop, mobile, desktop, watch we should have an responsive screen design

There are 2 ways which we can created responsive screen design

1. Layout Builder
2. MediaQuery.of()


# Layout Builder

From the builder propery you will get a `BoxConstraints` object. Examine the constraint's properties to decide what to display.

Example:
IF the maxWidth is > than the width breakpoint, return a `Scaffold` object with a row

# MediaQuery.of()

It gives the size, orientation of the current app. It is useful if you want to make decisions based on the complete context rather than the size of the particular widget.


# Other widgets for responsive design

* AspectRatio
* CustomSingleChildLayout
* CustomMultiChildLayout
* FittedBox
* FractionallySizedBox
* LayoutBuilder
* MediaQuery
* MediaQueryData
* OrientationBuilder

# Resource

Flutter Adaptive Layouts - [Click here to view](https://medium.com/flutter-community/developing-for-multiple-screen-sizes-and-orientations-in-flutter-fragments-in-flutter-a4c51b849434)