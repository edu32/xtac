# xtac
This is the source code of the compiler for the **xtab** computer programming language. It contains the compiler source and the standard library.

**xtab** is a self-hosted low-level compiled programming language.

## Compiling xtac

### Dependencies
`xtac` is a 64-bit compiler for **xtab** source files and emits x64 binaries. It has no external dependencies other than the Windows API and the C runtime library strictly through dynamic linking. `xtac` contains (and emits) 128-bit and 256-bit AVX instructions for IvyBridge or higher. `xtac` is multi-threaded and requires upto 1 GB of RAM to compile itself.

### Downloading
Download the `/source/` folder to your Windows machine. The `/source/.bin/` folder contains compiled x64 binaries and the `/source/compiler/` folder contains the compiler source. The current release of `xtac` is `/xtac.exe` and is in the same folder as `/source/`.

### Building
Run the file `xtac.exe`. This compiles all non-empty `*.xtab` files in the `/source/` folder (and sub-folders) and generates `/source/.bin/xtac.exe`. After resolving **all** issues, copy `/source/.bin/xtac.exe` to `/xtac.exe` (deleting the existing `xtac.exe` in the process) to have a new release of the `xtac` compiler.

## Code snippets

Factorial of first `n` natural numbers (ℕ)

```rust
fn factorial(n) {
    if n > 0 {
      return n * factorial(n - 1)
    }
    return 1
}
```

Generically add two numbers (or invoke overloaded `+` for non-numeric types)

```rust
fn add(a, b) = a + b

add(1, 2.5) // Output: 3.5
```

Generate and print the first `n` numbers of the fibonacci sequence

```javascript
/* Assume n >= 2 */
fn fibonacci(n) {
  yield 0 /* The first number of the fibonacci sequence is 0. */
  yield 1 /* The second number of the fibonacci sequence is 1. */  
  var last = 0, next = 1
  for let i = 2; i < n; ++i {
    const fib = last + next
    yield fib
    last = next
    next = fib
    // You can replace the previous two lines with (last, next) = (next, fib)
  }
}

each number in auto fibonacci(10) {
  println(number)
}
// Output: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34 and 55.
```

Print substrings of the names of the days of the week

```javascript
enum NameOfDay { Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday }
enum LengthToPrint { OneLetter, TwoLetters, ThreeLetters, WholeName }
fn printNameOfDay(nameOfDay, lengthToPrint) {
    const name = nameof(nameOfDay)
    switch lengthToPrint {
        case LengthToPrint.OneLetter    println(name[0])
        case LengthToPrint.TwoLetters   println(string{ text = name.text, length = 2 })
        case LengthToPrint.ThreeLetters println(string{ text = name.text, length = 3 })
        case LengthToPrint.WholeName    println(name)
        default assert with "Invalid lengthToPrint: #{lengthToPrint} (nameof(lengthToPrint)) for #{name}"
    }
}
var j = 0
for var i = 0; i < 7 /* MAX_NAMEOFDAY */; ++i {
    printNameOfDay(i as NameOfDay, j as LengthToPrint)
    if ++j > 4 { /* MAX_LENGTHTOPRINT */
        j = 0
    }
}
// Output: S, Mo, Tue, W, Th, Fri, S
```
