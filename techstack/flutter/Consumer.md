#flutter #notification #provider #changenotifier 

Consumer exposes instances of provided models, so one can display data and call methods on provided model.

The Consumer widget doesn't do any fancy work. It just calls [[Provider]].of in a new [[widget]], and delegates its build implementation to builder.

### Example from [[ChangeNotifierProvider]]
```dart
class MyHomePage extends StatelessWidget {
  const MyHomePage({Key key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Provider Class'),
      ),
      body: Center(
        child: Text( 
          '''
          Hi ${Provider.of<Person>(context).name;}!
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
Here, we need to call `Provider.of<Person>(context)` three times. This can be simplified by Consumer.
```dart
class MyHomePage extends StatelessWidget {
  const MyHomePage({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Consumer<Person>(
      builder: (context, person, _) {
        return Scaffold(
          appBar: AppBar(
            title: const Text('Provider Class'),
          ),
          body: Center(
            child: Text(
              '''
              Hi ${person.name}!
              You are ${person.age} years old''',
            ),
          ),
          floatingActionButton: FloatingActionButton(
            child: Text('+'),
            onPressed: () => person.increaseAge(),
          ),
        );
      }
    );
  }
}
```
[[techstack/flutter/Selector|Selector]] is similar to Consumer, but provides some fine control over when a [[widget]]s `build` method is called.