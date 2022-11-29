#flutter #buildcontext

BuildContext is an object that holds reference to the [widget](/techstack/flutter/widget.md)s own place in the [widget tree](/widget%20tree).

It can then look up the tree to its ancestors, which is what makes [InheritedWidgets](/InheritedWidgets) possible, among other things.

[extension](/techstack/flutter/extension.md) replaces some functions of BuildContext:

`BuildContext.read<Person>()` replaces `Provider.of<Person>(context, listen: false)`

`BuildContext.watch<Person>()` replaces `Provider.of<Person>(context)`

`BuildContext.select<Person>` completely removes the need to use a [Selector](/techstack/flutter/Selector.md).

#### Deprecated
```dart
Widget build(BuildContext context) {
  return Selector<Person, String>(
    selector: (context, p) => p.name,
    builder: (context, name, child) {
      return Text(name);
    },
  ),
}
```

#### Wired
```dart
Widget build(BuildContext context) {
  final name = context.select((Person p) => p.name);
  return Text(name);
}
```