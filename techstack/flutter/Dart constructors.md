To use [[Dart's named arguments]] you have to use curly brackets, like:
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
