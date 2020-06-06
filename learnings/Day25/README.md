<div align="center">
  <h1>Flutter - Day 25</h1>
  <p>Flutter Web</p>
</div>

To use Flutter web first we need to update flutter to the latest version once it is done

in the terminal do like below to enable web for flutter

```
flutter config --enable-web
```

To disable web

```
flutter config --no-enable-web
```

Once it is done create a new flutter as well do normally

```
flutter created application_name
```

Once it is done open an text editor now you could see a folder named `web`

inside the web folder you can see the `index.html` file like below

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta content="IE=Edge" http-equiv="X-UA-Compatible">
  <meta name="description" content="A new Flutter project.">

  <!-- iOS meta tags & icons -->
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black">
  <meta name="apple-mobile-web-app-title" content="food_web">
  <link rel="apple-touch-icon" href="icons/Icon-192.png">

  <!-- Favicon -->
  <link rel="shortcut icon" type="image/png" href="favicon.png"/>

  <title>food_web</title>
  <link rel="manifest" href="manifest.json">
</head>
<body>
  <!-- This script installs service_worker.js to provide PWA functionality to
       application. For more information, see:
       https://developers.google.com/web/fundamentals/primers/service-workers -->
  <script>
    if ('serviceWorker' in navigator) {
      window.addEventListener('load', function () {
        navigator.serviceWorker.register('flutter_service_worker.js');
      });
    }
  </script>
  <script src="main.dart.js" type="application/javascript"></script>
</body>
</html>
```

Now we can create the design/coding similar like what we do for the mobile application that is inside the main.dart file

Once the code is added you can run the program by listing the devices like

```
flutter devices
```

There you could see the chrome and web-driver option select chrome and run like below


`flutter run -d chrome`

Once it is done you can see the project running in web

To reload the page press `r` or `R`

# Report

When people from Angular / Reactjs comes here they feel it very hard bcoz each time they have to reload the page and we can create some static webpages using Flutter and not dynamic one as of now

# Output


<div align="center">
   <img src="../../assets/Day25/flutterweb.png" alt="flutter" height="300">
</div>