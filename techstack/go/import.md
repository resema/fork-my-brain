#go #packaging #package #GOPATH

The `import` statement tells the compiler where to look on disk to find the package you  want to import.

- Packages are found on disk based on their relative path to the directories referenced by the Go environment
- Packages in the **standard library** are found under where Go is installed
- Packages that are created by you live inside the `GOPATH`

The compiler will stop searching once it finds a packages that satisfies the import statement.

- Fo installation directory is the **first place** the compiler looks and the each directory listed in your `GOPATH` in the order that they-re listed
- Use go get command to fix those problems