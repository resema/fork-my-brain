#flutter 

In Flutter everything is a widget. It is arranged in a [[widget tree]]. This is connected to the [[element tree]].

Everything goes with a class belongs to the class.
- no static functions

There are two kinds of widgets, like [[stateless widget]] and [[stateful widget]].

### Receive data
All widgets can receive data via their [[constructors]]. But only [[stateful widget]] can have class properties where they can update values and re-run `build()`.