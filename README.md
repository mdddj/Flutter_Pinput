# PinPut
100% Dart based PIN input fiels for Flutter
## Overview
This widget accepts string os any length and calls the onSubmit method when all fields are filled.

<img src="https://raw.githubusercontent.com/Tkko/Flutter_PinPut/master/example/pinput_demo.gif" alt="drawing" width="180"/>

### Contents:
- [Installation](#installation)
- [Getting Started](#example)
- [Properties](#properties)

### Installation

Install the latest version [from pub](https://pub.dartlang.org/packages/pinput).

### Example

Import the package:

```dart
import 'package:flutter/material.dart';
import 'package:pinput/pinput.dart';

void main() => runApp(new PinPutTest());

class PinPutTest extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        theme: ThemeData(primaryColor: Colors.green, hintColor: Colors.green),
        home: Scaffold(
            body: Builder(
          builder: (context) => Center(
                child: PinPut(
                  onSubmit: (pin) => _showSnackBar(pin, context),
                ),
              ),
        )));
  }

  void _showSnackBar(String pin, context) {
    final snackBar = SnackBar(
      duration: Duration(seconds: 5),
      content: Container(
          height: 80.0,
          child: Center(
            child: Text(
              'Pin Submitted. Value: $pin',
              style: TextStyle(fontSize: 25.0),
            ),
          )),
      backgroundColor: Colors.greenAccent,
    );
    Scaffold.of(context).showSnackBar(snackBar);
  }
}
```

### Properties:

| Property   | Default               |
|------------|:---------------------:|
| onSubmit  | Function |
| fieldsCount  | 4 |
| isTextObscure  | false |
| fontSize  | 40.0 |
| borderRadius  | 5.0 |
| keybaordType  | number |
| keyboardAction  | next |

