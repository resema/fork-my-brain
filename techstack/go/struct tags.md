#go #metadata

```go
type T struct {
	Var string `example:"MyTag"`
}
```

- without tags field names could conflict with Go's rules about exported field names ([[naming convention]])

#### Example
- `encoding/json` recognizes a key of `json` and a vaue that controls the output

```go
package main

import (
	"encoding/json"
	"fmt"
	"log"
	"os"
	"time"
)

type User struct {
	Name          string    `json:"name"`
	Password      string    `json:"password"`
	PreferredFish []string  `json:"preferredFish"`
	CreatedAt     time.Time `json:"createdAt"`
}

func main() {
	u := &User{
		Name:      "Sammy the Shark",
		Password:  "fisharegreat",
		CreatedAt: time.Now(),
	}

	out, err := json.MarshalIndent(u, "", "  ")
	if err != nil {
		log.Println(err)
		os.Exit(1)
	}

	fmt.Println(string(out))
}
```

(Example used [[declaration and assignment]] abbreviation)