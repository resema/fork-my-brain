#flutter #basic 

In Flutter everything is a widget. It is arranged in a [widget tree](/widget%20tree). This is connected to the [element tree](/element%20tree).

Everything goes with a class belongs to the class.
- no static functions

There are two kinds of widgets, like [stateless widget](/techstack/flutter/stateless%20widget.md) and [stateful widget](/techstack/flutter/stateful%20widget.md).

### Receive data
All widgets can receive data via their [constructors](/constructors). But only [stateful widget](/techstack/flutter/stateful%20widget.md) can have class properties where they can update values and re-run `build()`.