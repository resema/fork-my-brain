#flutter #notification #provider #changenotifier 

Consumer exposes instances of provided models, so one can display data and call methods on provided model.

The Consumer widget doesn't do any fancy work. It just calls [provider](/techstack/flutter/provider.md).of in a new [widget](/techstack/flutter/widget.md), and delegates its build implementation to builder.

### Example from [ChangeNotifierProvider](/techstack/flutter/ChangeNotifierProvider.md)
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
[Selector](/techstack/flutter/Selector.md) is similar to Consumer, but provides some fine control over when a [widget](/techstack/flutter/widget.md)s `build` method is called.