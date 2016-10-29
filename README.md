# Hello World in Go
This is a simple hello world app using Golang.

## Golang

* https://golang.org/doc/code.html

Go code is typically kept in a single `workspace`. Workspace is a directory 
hierarchy with three directories at its root:

* `src` for source files
* `pkg` for packages
* `bin` for executables

The `go` tool builds source packages and installs the resulting binaries 
to the `pkg` and `bin` directories.

### GOPATH

The `GOPATH` environment variable specifies the workspace location.

```bash
$ mkdir $HOME/work
$ export GOPATH=$HOME/work
```

For convenience, add `bin` to the `PATH`

```bash
$ export PATH=$PATH:$GOPATH/bin
```

### Import paths

The packages from the standard library are given short import paths such 
as `"fmt"` and `"net/http"`. For your own packages, you must choose a base 
path that is unlikely to collide with future additions to the standard library 
or other external libraries.

If you keep your code in a source repository somewhere, then you should 
use the root of that source repository as your base path. For instance, 
if you have a [GitHub](https://github.com/) account at `github.com/user`, that should be your base 
path.

## Hello, World!

To compile and run a simple program, first choose a package path (for example
`github.com/user/hello`) and create a corresponding package directory 
inside your workspace:

```bash
$ mkdir $GOPATH/src/github.com/user/hello
```

Next, create file named `hello.go`:

```go
package main

import "fmt"

func main() {
	fmt.Printf("Hello, World.\n")
}
```

Now you can build and install that program with the `go` tool:

```bash
$ go install github.com/user/hello
```

`hello` command is now created and binary is installed to the workspace's
`bin` directory as `hello`.

Now you can run the program by typing its full path:

```bash
$ $GOPATH/bin/hello
Hello, World!
```

Or, as you have added `$GOPATH/bin` to your `PATH`, just type the binary name:

```bash
$ hello
Hello, World!
```
