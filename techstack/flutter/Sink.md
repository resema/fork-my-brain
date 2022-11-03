#flutter #async #observer #concurrency 

_Sinks_ are the first stop of [[event]]s in the [[observer pattern]]. A sink is the piece of the puzzle that you feed data into. It's kind of the central source for the whole process

In Dart `Sink` is an abstract class that more specific types of `sink`s implement. The most common of which is the [[techstack/flutter/StreamController|StreamController]]
