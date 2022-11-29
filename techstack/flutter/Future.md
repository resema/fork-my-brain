#flutter #async #future

The future is a prove you are waiting for something. It's a guarantee that a value will exist, but it isn't quite ready.
A placeholder for a value that will exist.

Most common scenario for using futures is when you're getting values over the [network](/network).

Futures are [thenable](/techstack/flutter/thenable.md).

### Catching Errors
- there's a method `catchError`
- with `try/catch` blocks