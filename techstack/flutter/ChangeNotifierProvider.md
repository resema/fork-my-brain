#flutter #provider #notification #dependencyinjection #notifier 

One of the class most often used. This is basically a [provider](/techstack/flutter/provider.md)-wrapper over a class that implements [ChangeNotifier](/techstack/flutter/ChangeNotifier.md).

### Example
```dart
import 'dart:collection'; // used in test.dart
import 'package:flutter/foundation.dart'; // used in test.dat
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
    return Scaffold(
      appBar: AppBar(
        title: const Text('Provider Class'),
      ),
      body: Center(
        child: Text(
          '''
          Hi ${context.select((Person p) => p.name)}!
          You are ${Provider.of<Person>(context).age} years old''',
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () => Provider.of<Person>(context, listen: false).increaseAge(),
      ),
    );
  }
}

```