#flutter 

Is a class that can be [[extended]] or [[mix-in]]-ed that provides a change [[notification]] [[API]] using [[VoidCallback]] for notifivations.

#### Practical terms
Other objects can _listen_ to a `ChangeNotifier` object. And, when the change notifier gets updated values, it can call a method called `notifyListeners()`, and then any of it's listeners will respond with an action.

The example shows a simple use case, but it presents also a problem. If one wants to use it in multiple [[widget]]s in different branches in your [[widget tree]], one would have to pass an instance of `ChangeNotifier` all around the [[widget tree]].

This is the exact problem that [[Provider]] solves! And the combination of it is the [[ChangeNotifierProvider]].

#### Example
```dart
import 'package:flutter/foundation.dart';
import 'package:flutter/material.dart';

class Person with ChangeNotifier {
  Person(this.name, this.age);

  final String? name;
  int age;

  // when `notifyListeners` is called, it will invoke
  // any callbacks that have been registered with an instance of this object
  // `addListener`.            
  void increaseAge() {
    this.age++;
    notifyListeners();
  }
}

void main() {
  var person = Person('Yohan', 25);
  
  // `addListener` is a method on the `ChangeNotifier` class,
  // which is mixed-in to the Person class    
  person.addListener(() {
    print('value updated!: ${person.age}');
  });      

  person.increaseAge();  // 26
}
```