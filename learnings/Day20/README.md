<div align="center">
  <h1>Flutter - Day 20</h1>
  <p>Flutter Widgets</p>
</div>

We will see some the Flutter Widgets today

1. SafeArea
2. Expanded
3. Wrap
4. Animated Container
5. Opacity
6. FutureBuilder
7. FadeTransistion
8. FloatingActionButton
9. PageView
10. Table

# 1. SafeArea

Based on the device if the text needs to be wrapped we should use safeArea which will take care of the below image

<div align="center">
   <img src="../../assets/Day20/safearea.png" alt="flutter" height="300">
 </div>

 to 

 <div align="center">
   <img src="../../assets/Day20/safe.png" alt="alignment" height="300">
 </div>

# 2.Expanded

To expand the widgets on the rows or columns we would use the `Expanded` widget which would fill the remaining spaces

<div align="center">
   <img src="../../assets/Day20/extrasace.png" alt="flutter" height="300">
 </div>

By using the Expanded widget we will fill the remaining space of the widget

<div align="center">
   <img src="../../assets/Day20/grow.png" alt="flutter" height="300">
 </div>

 Even we can add a flex factor if we have a competion

 <div align="center">
   <img src="../../assets/Day20/flexfacor.png" alt="flutter" height="300">
 </div>

# 3.Wrap

When we have multiple widgets on a single row we would face the error like below

<div align="center">
   <img src="../../assets/Day20/runoutofroom.png" alt="flutter" height="300">
 </div>

 For that we would use `Wrap` container like below

 <div align="center">
   <img src="../../assets/Day20/nextline.png" alt="flutter" height="300">
 </div>

 We can add the alignment like `Vertical` or `Horizontal`

 <div align="center">
   <img src="../../assets/Day20/direction.png" alt="flutter" height="300">
 </div>

 # 4.Animated Container

 There are implicit animations using the `AnimatedContainer`

 <div align="center">
   <img src="../../assets/Day20/animatedcontainer.png" alt="flutter" height="300">
 </div>

 # 5.Opacity

 If you want to hide a widget and have the space of the widget over there we can use the `Opacity` widget

 <div align="center">
   <img src="../../assets/Day20/opacity.png" alt="flutter" height="300">
 </div>

 # 6.FutureBuilder

 Both Flutter and Dart are async in nature suppose if we are loading a data from server and we want to show a loader during the load we can use FutureBuilder

  <div align="center">
   <img src="../../assets/Day20/async.png" alt="flutter" height="300">
 </div>

 <div align="center">
   <img src="../../assets/Day20/futruebuilder.png" alt="flutter" height="300">
 </div>

 What to show during loading and what to show once the loader is completed

 <div align="center">
   <img src="../../assets/Day20/displayonething.png" alt="flutter" height="300">
 </div>

<div align="center">
   <img src="../../assets/Day20/whendone.png" alt="flutter" height="300">
 </div>

<div align="center">
   <img src="../../assets/Day20/future.png" alt="flutter" height="300">
 </div>

<div align="center">
   <img src="../../assets/Day20/connectionstate.png" alt="flutter" height="300">
 </div>

 We should consider the error state also

 <div align="center">
   <img src="../../assets/Day20/errors.png" alt="flutter" height="300">
 </div>

 Other connection state

 <div align="center">
   <img src="../../assets/Day20/connectionstate.png" alt="flutter" height="300">
 </div>

 # 7.FadeTransistion

 To fade a widget we can use FadeTransistion this would be useful if u are showing a loader and to hide the loader once the data is received for that we would use the FadeTransistion Widget

 <div align="center">
   <img src="../../assets/Day20/fadetransistion.png" alt="flutter" height="300">
 </div>

 # 8.FloatingActionButton

 We can use the FAB button with simple steps inside Scaffold widget suppose if we want the FAB with the bottom navigation we can do it

 <div align="center">
   <img src="../../assets/Day20/fab.png" alt="flutter" height="300">
 </div>

 We can center the FAB inside the bottom navigation like below using `centerDocked` and to align it to the end we can use the `endDocked`

 <div align="center">
   <img src="../../assets/Day20/fab-center.png" alt="flutter" height="300">
 </div>


# 9.PageView

If we are having multiple page and we want to scroll it between the pages similar like the pageViewer in android we can do it using pageView

To have the pageview work we need to have the pageController and pageView widget 

<div align="center">
   <img src="../../assets/Day20/pagecontroller.png" alt="flutter" height="300">
 </div>


<div align="center">
   <img src="../../assets/Day20/pageview-wdig.png" alt="flutter" height="300">
 </div>


To scroll vertically we can change the scroll direction like below

<div align="center">
   <img src="../../assets/Day20/page-vertical.png" alt="flutter" height="300">
 </div>


# 10.Table

If you don't want a widget to be scrolled we can use it in the `Table` widget which will help the widget not to scroll

<div align="center">
   <img src="../../assets/Day20/table.png" alt="flutter" height="300">
 </div>