#flutter #async #callback

[[Future]].`then` takes a [[callback]], which will be executed when the future value resolves.

### Example
```dart
void main() {
   print("A");
   /// `Duration` is a dart class that defines a _duration of time_. 
   /// In this case, it represents 1 second.
   futurePrint(Duration(seconds: 1), "B").then((status) => print(status)); 
   print("C");
   futurePrint(Duration(seconds: 2), "D").then((status) => print(status));
   print("E");
 }

  /// All Future's are used by calling the callback that you give to "then" when the callback
  /// passed into the future completes. In this example, `Future.delayed` is a special
  /// constructor that just starts a timer (you tell it how long), and then when that timer
  /// finishes it calls it's callback. 
 Future futurePrint(Duration dur, String msg) {
   return Future.delayed(dur).then((_) => msg);
 }
```