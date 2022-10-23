#go #interface 

The dynamic type of an interface type is the current assigned type to the interface type. It is related to the [[static type]]

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

- the [[package]] [[reflect]] can be used to achieve the dynamic type of [[interface]] type value
  ```go
  reflect.TypeOf(i).PkgPath() // `main`
  reflect.TypeOf(i).Name()    // `T`
  reflect.TypeOf(i).String()  // `main.T`
```