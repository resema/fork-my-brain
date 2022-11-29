#dart #flutter #constructor #namedargument

To use [Dart's named arguments](/techstack/flutter/Dart's%20named%20arguments.md) you have to use curly brackets, like:
```dart
MyClass({String myString, int myInt}) {
	// ....
}
```

Short form to just initialize arguments:
```dart
MyClass(this.myVar);
```

Define special constructors:
```dart
class MyClass {
	MyClass.cstor(this.myVar) {
		myVar = 60;
	}
}
```
