#go #interface #inheritance

The use of a receiver with any function declaration declares a method that's bound to the specified receiver type.

```go
type T struct {
	//...
}

func(t *T) foo() {
	//...
}
```

- it's best practice to declare methods using pointer receiver
	- whether we use a value or pointer fo the receiver type to make the method call, the compile **will reference or dereference the value if necessary** to support the call
	- many methods **need to manipulate** the state of the value
- unlike when you call methods **directly  from values and pointers** when you **call a method via an [[interface]] type value**, the **rules are different**