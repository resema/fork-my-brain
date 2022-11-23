#flutter #observer #stream #observer 

Streams are an asynchronous programming pattern, often called [[observable]]s in other languages. From a high-level, streams provide a way for classes or objects to be notified when events happen.

[[StreamBuilder]] makes use of streams.

It is part of the [[techstack/flutter/observer pattern|observer pattern]].

#### Async umbrella
- [[techstack/flutter/Future|Future]]
- [[techstack/flutter/Completer|Completer]]
- [[techstack/flutter/async-await|async/await]]
- [[async for]]
- [[techstack/flutter/Stream|Stream]]
- [[techstack/flutter/Sink|Sink]]
- [[techstack/flutter/listen|listen]]

### Implementing Streams
```dart
import 'dart:async';

class Cook {
  void prepareOrder(newOrder) {
    print("preparing $newOrder");
  }
}

/// First, I made three classes that will let us be sure the
/// right type of data is being passed into the controller,
/// but also let us determine what sub-type of `Order` it is.
class Order {}
class Burger extends Order {}
class Fries extends Order {}


class BurgerStand {
  StreamController<Order> _controller = new StreamController.broadcast();
  /// Now, there are two cooks, one for each cooking device.
  Cook grillCook = new Cook();
  Cook fryCook = new Cook();

  /// This is where the interesting part starts. Both of these getters
  /// are listening to the same stream, but only emitting the 
  /// events that receive the correct types. 
  /// It's explained in more detail below.
  Stream get onNewBurgerOrder => 
      _controller.stream.where((Order order) => (order is Burger));
  Stream get onNewFryOrder =>
      _controller.stream.where((Order order) => (order is Fries));

  /// In this method, there are now _two_ listeners on the same
  /// stream, but will only pass the event to the correct cook.
  void deliverOrderToCook() {
    onNewBurgerOrder.listen((newOrder) {
      grillCook.prepareOrder(newOrder);
    });

    onNewFryOrder.listen((newOrder) {
      fryCook.prepareOrder(newOrder);
    });
  }

  void newOrder(Order order) {
    _controller.add(order);
  }
}

main() {
  var burgerStand = new BurgerStand();
  burgerStand.deliverOrderToCook();
  
  /// Now, the `newOrder` method expects an `Order` type (or subtype).
  burgerStand.newOrder(new Burger()); 
  burgerStand.newOrder(new Fries());
}
```