#flutter  #buildcontext 

Under the hood, that `of` method is looking up the [[widget tree]] for the next parent [[widget]] that is of type `Theme`, and grabbing that property.

```dart
@override
Widget build(context) {
	return new Text('Hello World',
		style: new TextStyle(color: Theme.of(context).primaryColor),
	);
}
```