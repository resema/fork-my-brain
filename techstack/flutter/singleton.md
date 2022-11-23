#flutter #pattern #singleton

Singleton is an single instance within the complete system. There are multiple solutions to this scenario in the different languages.

Flutter does it like this:
```dart
class MySingleton {
	static final MySingleton _instance = MySingleton._internal();

	factory MySingleton() {
		return _instance;
	}

	MySingleton._internal();
}
```