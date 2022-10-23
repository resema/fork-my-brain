#go #interface #composition

Composition of [[interface]]s can be found throughout the [[standard library]].
``` go
type ReadWriter interface {
	Reader
	Writer
}
```