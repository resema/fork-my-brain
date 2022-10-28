#flutter #statemanagement #dependencyinjection

Is a mix between [[state management]] and [[dependency injection]]. Some call it 'Inherited [[Widget]]s for humans'.

- Provider gives us an easy, low [[boiler-plate]] way to separate business logic from our [[widget]]s in apps
- it makes it easy to re-use and re-factor business logic

#### What does Provider do for me?
- separates your [[state]] from your [[UI]]
- manages rebuilding [[UI]] based on [[state change]]s

#### Most basic example

https://dartpad.dev/?id=e66e420f2f0201c772f73819711bf290

```dart
import 'dart:collection'; // used in test.dart
import 'package:flutter/foundation.dart'; // used in test.dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';

// Provider will _provide_ an instance of this class to any widget
class Person {
  Person({this.name, this.age});

  final String? name;
  final int? age;
}

// Provider is also a widget, so we wrap our app inside the Provider widget
// It uses a property called `create` to make an instance of the provided class
void main() {
  runApp(
    Provider(
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
	      // this string is where we use Provider to fetch the instance
	      // of `Person` created above in the `create` property
          '''
          Hi ${Provider.of<Person>(context).name},
          Hi again ${context.select((Person p) => p.name)}!
          You are ${Provider.of<Person>(context).age} years old''',
        ),
      ),
    );
  }
}

```