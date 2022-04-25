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
