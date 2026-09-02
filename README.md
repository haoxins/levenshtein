===========

Go package to calculate the [Levenshtein Distance](http://en.wikipedia.org/wiki/Levenshtein_distance)

The library is fully capable of working with non-ascii strings. But the strings are not normalized. That is left as a user-dependant use case. Please normalize the strings before passing it to the library if you have such a requirement.
- https://blog.golang.org/normalization

#### Limitation

As a performance optimization, the library can handle strings only up to 65536 characters (runes). If you need to handle strings larger than that, please pin to version 1.0.3.

Example
-------

```go
package main

import (
	"fmt"

	"github.com/haoxins/levenshtein"
)

func main() {
	s1 := "kitten"
	s2 := "sitting"
	distance := levenshtein.ComputeDistance(s1, s2)
	fmt.Printf("The distance between %s and %s is %d.\n", s1, s2, distance)
	// Output:
	// The distance between kitten and sitting is 3.
}
```
