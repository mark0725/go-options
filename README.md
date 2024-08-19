# go-options
go lib options


## Install

Install the package with:

```
go get github.com/mark0725/go-options
```

Import it with:

```
import "github.com/mark0725/go-options"
```


## Example

```
package main

import (
	"fmt"

	"github.com/mark0725/go-options"
)

func LibFnMapOptions(opts ...options.Option) {
	o := options.NewMapOptions(opts...)
	fmt.Println(o)
}

type MyOptions struct {
	A int
	B string
}

func LibFnOptions(opts ...options.Option) {
	o := MyOptions{}

	err := options.NewOptions(&o, opts...)

	if err != nil {
		fmt.Println(err)
		return
	}
	fmt.Printf("%#v\n", o)

}

func main() {
	LibFnMapOptions(options.With("a", 1), options.With("b", 2), options.With("c", 3))

	LibFnOptions(options.With("A", 1), options.With("B", "hello"))
}
```

## License

MIT
