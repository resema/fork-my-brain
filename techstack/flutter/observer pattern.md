#flutter #async #observer #concurrency 

There are three pieces of the observer pattern:
- [Sink](/techstack/flutter/Sink.md)s
- [Stream](/techstack/flutter/Stream.md)
- [Subscriber](/techstack/flutter/Subscriber)

[Stream](/techstack/flutter/Stream.md)s are properties on the [Sink](/techstack/flutter/Sink.md). When the sink needs to notify listeners of new events, it does so via [Stream](/techstack/flutter/Stream.md)s.

[Subscriber](/techstack/flutter/Subscriber)s are the external classes or objects that are waiting to be notified. This is done by listening to streams.