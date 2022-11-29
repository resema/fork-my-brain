#go #packaging #package #GOPATH

The `import` statement tells the compiler where to look on disk to find the package you  want to import.

- Packages are found on disk based on their relative path to the directories referenced by the Go environment
- Packages in the **standard library** are found under where Go is installed
- Packages that are created by you live inside the [GOPATH](/techstack/go/GOPATH.md)

The compiler will stop searching once it finds a packages that satisfies the import statement.

- Fo installation directory is the **first place** the compiler looks and the each directory listed in your `GOPATH` in the order that they-re listed
- Use go get command to fix those problems

#### remote imports

```go
import "github.com/spf13/viper"
```

- `go build` search the `GOPATH` for this package location on disk
- `go get` can be used to fetch the package from [RCS](/revision%20control%20system) and places the code inside the `GOPATH` at the location that matches the [URL](/techstack/network/URL.md)

#### named imports
- performed by giving one of the packages a new name to the left of the `import` statement
- sometimes you may need to import a package that you don't need to reference identifiers from
	- use the `blank identifier`
	  ```go
	  import _ "mypackage/package"
```
