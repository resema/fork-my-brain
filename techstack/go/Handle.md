#go #network #http 

Handle registers the [[Handler]] for the given pattern in the DefaultServeMux. The documentation for [[ServeMux]] explains how patterns are matched.

```go
// Handle registers the handler for the given pattern
// in the DefaultServeMux.
// The documentation for ServeMux explains how patterns are matched.
func Handle(pattern string, handler Handler) {
	DefaultServeMux.Handle(pattern, handler)
}
```

#### Example
```go
package main

import (
	"fmt"
	"log"
	"net/http"
	"sync"
)

type countHandler struct {
	mu sync.Mutex // guards n
	n  int
}

func (h *countHandler) ServeHTTP(w http.ResponseWriter, r *http.Request) {
	h.mu.Lock()
	defer h.mu.Unlock()
	h.n++
	fmt.Fprintf(w, "count is %d\n", h.n)
}

func main() {
	http.Handle("/count", new(countHandler))
	log.Fatal(http.ListenAndServe(":8080", nil))
}
```
- `countHandler` must implement the [[interface]] of a [[Handler]]
	- `ServeHTTP(ResponseWriter, *Request`
		- takes a [[ResponseWriter]] and a [[Request]]