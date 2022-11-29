#go #interface 

The dynamic type of an interface type is the current assigned type to the interface type. It is related to the [static type](/techstack/go/static%20type.md)

```go
type I interface {
	foo()
}

type T struct {}
func (T) foo() {}

func main() {
	var i I = T{} // T is the dynamic type
}
```

- the [package](/package) [reflect](/reflect) can be used to achieve the dynamic type of [interface](/techstack/go/interface.md) type value
  ```go
  reflect.TypeOf(i).PkgPath() // `main`
  reflect.TypeOf(i).Name()    // `T`
  reflect.TypeOf(i).String()  // `main.T`
```