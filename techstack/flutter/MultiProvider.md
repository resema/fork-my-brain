#flutter #provider #dependencyinjection #multi

`MultiProvider` let's you pass in a list of providers without nesting anything.

### Example
```dart
void main() {
  runApp(
    // You can wrap multiple providers 
    MultiProvider(
      providers: [
        Provicer<Person>(create: (_) => Person(name: 'Yohan', age: 25)),
        FutureProvider<String>(create: (context) => Home().fetchAddress),
      ],
      child: MyApp(),
    ),
  );
}
```