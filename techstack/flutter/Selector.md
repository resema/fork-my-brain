#flutter #changenotifier #consumer #buildcontext 

In a nutshell, `Selector` is a [Consumer](/techstack/flutter/Consumer.md) that allows you to define exactly which properties from a model you care about.

Can be omitted when [extension](/techstack/flutter/extension.md) are used to the [BuildContext](/techstack/flutter/BuildContext.md).

### Example
```dart
import 'dart:collection';
import 'package:flutter/foundation.dart';
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';

class Person with ChangeNotifier {
  Person({required this.name, required this.age});

  final String name;
  int age;

  void increaseAge() {
    this.age++;
    notifyListeners();
  }
}

void main() {
  runApp(
    ChangeNotifierProvider(
      create: (_) => Person(name: "Yohan", age: 25),
      child: MyApp(),
    ),
  );
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  const MyHomePage({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Selector<Person, String>(
      selector: (BuildContext context, Person person) => person.name,
      builder: (context, String name, child) {
        return Scaffold(
          appBar: AppBar(
            title: Text("${name} -- ${Provider.of<Person>(context).age} yrs old"),
          ),
          body: child,
        );
      },
      child: Center(
        child: Text('Hi this represents a huge widget! Like a scrollview with 500 children!'),
      ),
    );
  }
}
```