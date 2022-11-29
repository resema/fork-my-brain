#flutter #observer #stream #observer 

Streams are an asynchronous programming pattern, often called [observable](/observable)s in other languages. From a high-level, streams provide a way for classes or objects to be notified when events happen.

[StreamBuilder](/StreamBuilder) makes use of streams.

It is part of the [observer pattern](/techstack/flutter/observer%20pattern.md).

#### Async umbrella
- [Future](/techstack/flutter/Future.md)
- [Completer](/techstack/flutter/Completer)
- [async/await](/techstack/flutter/async-await.md)
- [async for](/async%20for)
- [Stream](/techstack/flutter/Stream.md)
- [Sink](/techstack/flutter/Sink.md)
- [listen](/techstack/flutter/listen)

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