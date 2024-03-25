<!--
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages).

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages).
-->


## Getting started

You can use instant translation simply by calling the library and you can translate into all languages


### Example  
```dart
import 'package:flutter/material.dart';
import 'package:translatlkt/translatelkt.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatefulWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  var desc = ''; // Initialize desc

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.center,
          children: [
            SizedBox(
              width: double.infinity,
            ),
            Text(desc),
            ElevatedButton(
              onPressed: () {
                translateAndSetState();
              },
              child: Text("Translate"),
            )
          ],
        ),
      ),
    );
  }

  // Function to translate and set the state
  void translateAndSetState() async {
    var translatedText = await translateLkt('en', 'ar', 'hello, how are you');
    setState(() {
      desc = translatedText;
    });
  }
}

```
