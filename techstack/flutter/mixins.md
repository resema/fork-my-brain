#flutter #OOP #inheritance #mixin

Mixins are a way of reusing a class's code in different class hierarchies. Like [[inheritance]] but we don't need to have parent classes to provide functionality between related classes.

#### Example
```dart
class Employee {
	void clockIn() {...}
}

mixin Medical {
	int takeTemperature() {...}
}


class Nurse extends Employee with Medical{}
// doctor has not to clock in but can take temp
class Doctor with Medical {}
class Bartender extends Employee {}
```

- Flutter provides different mixins out of the box, like
	- `EquatableMixin`
		- overrides the `operator==`