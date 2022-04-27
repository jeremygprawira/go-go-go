# go-go-go
Jeremy's so-called cheat sheet for everything about Go language.

This is simply a personal modification and addition from the [golang-cheat-sheet](https://github.com/a8m/golang-cheat-sheet/blob/master/README.md) repository.
Shoutout to Ariel Mashraki for giving me the inspiration to create this.

References will be shown after all the cheats.

# Index
**Go 101**
1. [Basic Syntax](#basic-syntax)
2. [Operators](#operators)
    * [Arithmetic](#arithmetic)
    * [Comparison](#comparison)
    * [Logical](#logical)
    * [Other](#other)
3. [Declarations](#declarations)
4. [Functions](#functions)
    * [Functions as values and closures](#functions-as-values-and-closures)
    * [Variadic Functions](#variadic-functions)
5. [Built-in Types](#built-in-types)
6. [Type Conversions](#type-conversions)
7. [Packages](#packages)
8. [Control structures](#control-structures)
    * [If](#if)
    * [Loops](#loops)
    * [Switch](#switch)
9. [Arrays, Slices, Ranges](#arrays-slices-ranges)
    * [Arrays](#arrays)
    * [Slices](#slices)
    * [Operations on Arrays and Slices](#operations-on-arrays-and-slices)
10. [Maps and Make](#maps-and-make)
11. [Structs](#structs)
12. [Pointers](#pointers)
13. [Errors, Panic, Recover](#errors-panic-recover)

**Go 201**
Later!

# Basic Syntax

## Hello World
file `main.go`:
``` go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

To run the file: `$ go run main.go`

# Operators
### Arithmetic
|Operator|Description|
|--------|-----------|
|`+`|addition|
|`-`|subtraction|
|`*`|multiplication|
|`/`|quotient or division|
|`%`|remainder|
|`&`|(bitwise) AND|
|`\`|(bitwise) OR|
|`^`|(bitwise) XOR|
|`&^`|(bitwise) AND NOT, or CLEAR|
|`<<`|left shift|
|`>>`|right shift|

### Comparison
|Operator|Description|
|--------|-----------|
|`==`|equal|
|`!=`|not equal|
|`<`|less than|
|`<=`|less than or equal|
|`>`|greater than|
|`>=`|greater than or equal|

### Logical
|Operator|Description|
|--------|-----------|
|`&&`|AND|
|`\|\`|OR|
|`!`|NOT|

### Other
|Operator|Description|
|--------|-----------|
|`&`|address of/pointer|
|`*`|dereference pointer|
|`<-`|send or receive operator (ref. [Channels](#channels))|

## Declarations
Types goes after identifier!
``` go
// declaration without initialization
var foo int
// declaration with initialization
var foo int = 42
// declare multiple variables with initializations
var foo, bar int = 42, 1302
// The general, simplest way to create and initialize
foo := 42
// Constant
const fooC = "constant"
```
Note: iota could be explained sooner if time allows.

## Functions
``` go
// Simple way to create a function
func functionName() {}

// func with parameters
func functionName(param1 string, param2 int) {}

// func with same data type parameters
func functionName(param1, param2 int) {}

// return parameter from the function
func functionName() int {
   return 32
}

// return multiple values at once
func functionName() (int, string) {
   return 32, "abc"
}

// return multiple values existed in variables
func functionName() (a int, b string) {
   n = 32
   s = "bac"
   return // return simply like this
}

var x, y = functionName()

```

### Functions as values and closures
This will be discussed later as it is quite confused me :).

### Variadic Functions
Also would be disccused later.

## Built-in Types
```go
bool

string

int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr

byte // alias for uint8

rune // alias for int32 ~= a character (Unicode code point) - very Viking

float32 float64

complex64 complex128
```
All Go's predeclared identifiers are defined in the [builtin](https://golang.org/pkg/builtin/) package. 

## Type Conversions
```go
var i int = 42
var f float64 = float64(i)
var u uint = uint(f)

// alternative syntax
i := 42
f := float64(i)
u := uint(f)
```

## Packages
This is package and how to declare it: `package main`
* To declare it, it should be positioned at the top of the file
* Executables are in the `main` package
* If you want to take a package from outside files, or imported file you can simply take the last name of the import path. Example: `math/rand`, the package is `rand`.
* Global package: Upper-case, visible and accesible from other packages.
* Non-global: Lower-case, invisble and non-accesible from other packages.

## Control structures

### If
```go
func main() {
	// Basic one
	if x > 10 {
		return x
	} else if x == 10 {
		return 10
	} else {
		return -x
	}

	// You can put one statement before the condition
	if a := b + c; a < 42 {
		return a
	} else {
		return a - 42
	}

	// Type assertion inside if
	var val interface{} = "foo"
	if str, ok := val.(string); ok {
		fmt.Println(str)
	}
}
```
