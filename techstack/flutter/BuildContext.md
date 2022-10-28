#flutter 

BuildContext is an object that holds reference to the [[widget]]s own place in the [[widget tree]].

It can then look up the tree to its ancestors, which is what makes [[InheritedWidgets]] possible, among other things.

[[extension]] replaces some functions of BuildContext:

`BuildContext.read<Person>()` replaces `Provider.of<Person>(context, listen: false)`

`BuildContext.watch<Person>()` replaces `Provider.of<Person>(context)`

`BuildContext.select<Person>` completely removes the need to use a [[Selector]].

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