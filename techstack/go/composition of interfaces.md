#go #interface #composition

Composition of [interface](/techstack/go/interface.md)s can be found throughout the [standard library](/standard%20library).
``` go
type ReadWriter interface {
	Reader
	Writer
}
```