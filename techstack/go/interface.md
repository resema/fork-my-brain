#go #inheritance #interface 

- interfaces are implemented **implicitly**
- they have [[dynamic type]] and [[static type]]
- interface type value is `nil` iff both [[dynamic type]] and [[dynamic value]] are `nil`

- Methods declared with **pointer [[receiver]]** can **only** by called by interface type values that contain pointer.

- Methods declared with **value [[receiver]]** can be called by interface type values that contain **both values and pointers**

```go
type I interface {
	f1(name string)
	f2(name string) (error, float32)
	f3() int64
}
```

- no particular implementation is enforced
- it's enough thay type defines methods with desired names and signatures to implement an interface
  ```go
  type T int64

  func (T) f1(name string) {
	  fmt.Println(name)
  }
  func (T) f2(name string) (error, float32) {
	  return nil, 10.2
  }
  func (T) f3() int64 {
	  return 10
  }
```
- values of type T can be passed to **any function accepting I as a parameter**