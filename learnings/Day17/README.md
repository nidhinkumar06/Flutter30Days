<div align="center">
  <h1>Flutter - Day 17</h1>
  <p>UserInterface - Assets and Images</p>
</div>

# Specifying assets

Flutter uses `pubspec.yaml` file which is located at the root of your project.

```
flutter:
  assets:
    - assets/my_icon.png
    - assets/background.png
```

To include all assets under a directory specify the directory name with / character at the end.

```
flutter:
  assets:
    - directory/
    - directory/subdirectory/
```

# Loading images

To load an image use the `AssetImage` Class in a widgets `build()` 

```
Widget build(BuildContext context) {
  return Image(image: AssetImage('graphics/background.png'));
}
```

# Asset Image in package dependency

To load an image from an package dependency, the package argument must be provided to the `AssetImage`

```
.../pubspec.yaml
.../icons/heart.png
.../icons/1.5x/heart.png
.../icons/2.0x/heart.png
...etc.

```

To load the image use:

```
AssetImage('icons/heart.png', package: 'my_icons')
```

# Platform assets

### Updating the app icon

Updating a Flutter application’s launch icon works the same way as updating launch icons in native Android or iOS applications.

To replace the icon in android go to android src -> res -> mipmap(dimensions)

similarly the same for iOS

### Updating the launch screen

#### Android

To add a “splash screen” to your Flutter application, navigate to `.../android/app/src/main`. In `res/drawable/launch_background.xml`, use this layer list drawable XML to customize the look of your launch screen. The existing template provides an example of adding an image to the middle of a white splash screen in commented code. You can uncomment it or use other drawables to achieve the intended effect.

#### iOS

To add an image to the center of your “splash screen”, navigate to `.../ios/Runner`. In `Assets.xcassets/LaunchImage.imageset`, drop in images named LaunchImage.png, LaunchImage@2x.png, LaunchImage@3x.png. If you use different filenames, update the Contents.json file in the same directory.