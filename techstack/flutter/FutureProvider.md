#flutter #dependencyinjection #provider 

FutureProvider has a initial value, which widgets can use until the `Future` value is resolved. When resolved, it the `FutureProvider` will tell it's descendents to rebuild, using the new value.

Importantly, this means that the widgets who rely on the value of a future provider will only rebuild once. It will display the initial value, and then the provided future value, and then won't rebuild again.

```dart 
import 'dart:collection';
import 'package:flutter/foundation.dart';
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';


class Person {
  Person({required this.name, required this.age});

  final String name;
  int age;
}

class Home {
  final String city = "Portland";

	// the value that will be provided must be a `Future`!
  Future<String> get fetchAddress {
    final address = Future.delayed(Duration(seconds: 2), () {
      return '1234 North Commercial Ave.';
    });

    return address;
  }
}

void main() {
  runApp(
    Provider<Person>(
      create: (_) => Person(name: 'Yohan', age: 25),
			
			// The future provider provides a String value, 
      // rather than the entire class of Home
      child: FutureProvider<String>(
        create: (context) => Home().fetchAddress,
        // this will be displayed in the meantime
        // until a new value is provided from the future
        initialData: "fetching address...",
        child: MyApp(),
      ),
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
        title: Text("Future Provider"),
      ),
      body: Padding(
        padding: const EdgeInsets.all(8.0),
        child: Center(
          child: Consumer<Person>(
            builder: (context, Person person, child) {
              return Column(
                children: <Widget>[
                  Text("User profile:"),
                  Text("name: ${person.name}"),
                  Text("age: ${person.age}"),
                  Consumer<String>(builder: (context, String address, child) {
                    return Text("address: $address");
                  }),
                ],
              );
            },
          ),
        ),
      ),
    );
  }
}

```

In the example is a ugly part, with this approach two [[Provider]]s are needed. One nested inside the other. That this is not getting out of hand uses [[techstack/flutter/MultiProvider|MultiProvider]].

[[techstack/flutter/StreamProvider|StreamProviders]] work so similarly to `FutureProvider`, but provides streamed values.