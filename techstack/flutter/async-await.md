#flutter #async #concurrency 

Keywords `async` and `await` are the easiest way to wrap your head around [[async]] programming.

Any function can be marked as `async`, and then tell that function to `await` async processes to finish before moving on.

With this keywords you can make asynchronous code synchronous.

### Example
```dart
/// Mark the function as asynchronous with the `async` keyword.
void main() async {
	print("A");
  /// Mark the line (which should be a future) you want to pause on with `await`.
  await futurePrint(Duration(milliseconds: 1000), "B")
		.then((status) => print(status));
	print("C");
  await futurePrint(Duration(milliseconds: 500), "D")
		.then((status) => print(status));
  print("E");
}

Future futurePrint(Duration dur, String msg) {
	return Future.delayed(dur).then((onValue) => msg);
}
```