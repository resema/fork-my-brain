The static type of an interface type is the base type to the interface type. It is related to the [[dynamic type]]

```go
type I interface {
	foo()
}

type T struct {}
func (T) foo() {}

func main() {
	var i I = T{} // I is the static type
}
