#flutter 

Is a class that can be [[extended]] or [[mix-in]]-ed that provides a change [[notification]] [[API]] using [[VoidCallback]] for notifivations.

#### Practical terms
Other objects can _listen_ to a `ChangeNotifier` object. And, when the change notifier gets updated values, it can call a method called `notifyListeners()`, and then any of it's listeners will respond with an action.

#### Example
```dart
void main() {
	
}
```