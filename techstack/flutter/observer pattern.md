#flutter #async #observer #concurrency 

There are three pieces of the observer pattern:
- [[Sink]]s
- [[Stream]]
- [[techstack/flutter/Subscriber|Subscriber]]

[[Stream]]s are properties on the [[Sink]]. When the sink needs to notify listeners of new events, it does so via [[Stream]]s.

[[techstack/flutter/Subscriber|Subscriber]]s are the external classes or objects that are waiting to be notified. This is done by listening to streams.