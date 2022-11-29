#flutter #provider #proxy

It's just a [proxy](/proxy):
- ProxyProvider0, ProxyProvider2, 3, 4, 5, 6
- [ChangeNotifierProxyProvider](/ChangeNotifierProxyProvider), 2, 3, 4, 5, 6
- [ListenableProxyProvider](/ListenableProxyProvider), 2, 3, 4, 5, 6

### Example
```dart
class Person with ChangeNotifier {
  Person({this.name, this.age});

  final String name;
  int age;

  void increaseAge() {
    this.age++;
    notifyListeners();
  }
}

class Job with ChangeNotifier {
  Job(
    this.person, {
    this.career,
  });

  final Person person;
  String career;
  String get title {
    if (person.age >= 28) return 'Dr. ${person.name}, $career PhD';
    return '${person.name}, Student';
  }
}

void main() {
  runApp(
    MultiProvider(
      providers: [
        // you must first provider the object that will be passed to the proxy    
        ChangeNotifierProvider<Person>(create: (_) => Person(name: 'Yohan', age: 25)),
        // Because the ChangeNotifierProxyProvider is being used,
        // each class used must be of ChangeNotifier type    
        ChangeNotifierProxyProvider<Person, Job>(
          // first, create the _proxy_ object, the one that you'll use in your UI
          // at this point, you will have access to the previously provided objects                
          create: (BuildContext context) => Job(Provider.of<Person>(context, listen: false)),
          // next, define a function to be called on `update`. It will return the same type
          // as the create method.   
          update: (BuildContext context, Person person, Job job) => Job(person, career: 'Vet'),
        ),
      ],
      child: MyApp(),
    ),
  );
}
```