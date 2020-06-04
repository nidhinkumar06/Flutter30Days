<div align="center">
  <h1>Flutter - Day 23</h1>
  <p>Flutter Widgets</p>
</div>

# FittedBox

Most of the widgets are boxes we can lay them of, stack them, nest them inside other widget

But what if the widget doesn't fit inside another widget then we will use the `FittedBox` widget

<div align="center">
   <img src="../../assets/Day23/doesntfit.png" alt="flutter" height="300">
</div>

<div align="center">
   <img src="../../assets/Day23/fittedbox.png" alt="flutter" height="300">
</div>

and a BoxFit to contain like below

<div align="center">
   <img src="../../assets/Day23/fit.png" alt="flutter" height="300">
</div>

Now the widget will be fitted inside the other widget like below

<div align="center">
   <img src="../../assets/Day23/clipt.png" alt="flutter" height="300">
</div>

There are options like `Width`

<div align="center">
   <img src="../../assets/Day23/width.png" alt="flutter" height="300">
</div>

`Fill`

<div align="center">
   <img src="../../assets/Day23/fill.png" alt="flutter" height="300">
</div>

`None` option

<div align="center">
   <img src="../../assets/Day23/none.png" alt="flutter" height="300">
</div>

# Layout Builder

Layout Builder is like what should be shown in a screen like if it is a mobile view how the screen should be shown.Suppose if it is a tablet can be show a two screens in a single page

<div align="center">
   <img src="../../assets/Day23/layoutbuilder.png" alt="flutter" height="300">
</div>

# Absorb pointer

Absorb pointer is like a disabling a button or disabling the scroll view but if you have a bunch of widgets inside a single page u can use the Absorb pointer like below

<div align="center">
   <img src="../../assets/Day23/ absorbpointer.png" alt="flutter" height="300">
</div>

Absorbing false

<div align="center">
   <img src="../../assets/Day23/absorbingfalse.png" alt="flutter" height="300">
</div>


# Transform Widget

Transform widget is like rotating an widget or to give an custom effet similar like the Ramotion kind of card view. It can be used for Cardview, Carousel, menu

# Backdrop Filter

Backdrop filter is to add filter for the images like blurring, skew

# Align

How to align a text inside a container to center align we can use the `Center` widget but what we do if we want it to align `BottomRight` and `TopLeft` how it can be done.

<div align="center">
   <img src="../../assets/Day23/aligne.png" alt="flutter" height="300">
</div>

Or if we need it at the top left

<div align="center">
   <img src="../../assets/Day23/topleft.png" alt="flutter" height="300">
</div>

and even we can give values based on the x and y axis 

<div align="center">
   <img src="../../assets/Day23/values.png" alt="flutter" height="300">
</div>

# Positioned

In a stack if u want to position an widget you can use the positioned widget using that we can position the widget on left, top, right, bottom 

<div align="center">
   <img src="../../assets/Day23/positioned.png" alt="flutter" height="300">
</div>

Even we can fill the widget in positioned like below

<div align="center">
   <img src="../../assets/Day23/positionfill.png" alt="flutter" height="300">
</div>

# AnimatedBuilder

To animate an widget we would use the animated builder widget where we can animate an widget

<div align="center">
   <img src="../../assets/Day23/animation-tween.png" alt="flutter" height="300">
</div>

# Dismissable

Swiping an list item to delete item we can use the Dismissable widget

<div align="center">
   <img src="../../assets/Day23/dismissable.png" alt="flutter" height="300">
</div>

To add the dismissable widget in a stateful widget we can use the `onDismissed` widget like below

<div align="center">
   <img src="../../assets/Day23/staefultwidget.png" alt="flutter" height="300">
</div>

# SizedBox

SizeBox is like adding a perfect width and height for a button/widget. We can give the width and the height for the widget or else we can give the `double.infinity` where we can widget/button based on the size available
Suppose if we give `double.infinity` for both width and height means it fill the entire place instead we can give other option like `sizedBox.expand`

<div align="center">
   <img src="../../assets/Day23/sizedbox.png" alt="flutter" height="300">
</div>

Expand

<div align="center">
   <img src="../../assets/Day23/expand.png" alt="flutter" height="300">
</div>