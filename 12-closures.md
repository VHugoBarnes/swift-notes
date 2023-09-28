# Swift Closures

Closures are self-contained blocks of code that can be passed around and used in your code. They are similar to lambdas in other programming languages.

## Closures

Basic closure syntax:

```swift
{ (params) -> returnType in
    // Code body
}
```

### Example:

Using the provided names:

```swift
let names = ["Christian", "Ricardo", "Juan Gabriel", "Edgar", "Freddy"]

var reversedNames = names.sorted(by: { (s1: String, s2: String) -> Bool in
    return s1 > s2
})
```

## Trailing Closures

If a closure is the last argument to a function, it can be passed as a trailing closure, outside the function's parentheses:

```swift
reversedNames = names.sorted { $0 > $1 }
```

## Capture Values

Closures can capture constants and variables from the surrounding context in which they are defined. 

```swift
func makeIncrementer(forIncrement amount: Int) -> () -> Int {
    var runningTotal = 0
    func incrementer() -> Int {
        runningTotal += amount
        return runningTotal
    }
    return incrementer
}

let incrementByTen = makeIncrementer(forIncrement: 10)
incrementByTen() // Outputs 10
incrementByTen() // Outputs 20
```

## Escaping Closures

If a closure is passed as an argument to a function and is invoked after the function returns, the closure is escaping. Use the `@escaping` attribute.

```swift
var completionHandlers: [() -> Void] = []

func someFunctionWithEscapingClosure(completionHandler: @escaping () -> Void) {
    completionHandlers.append(completionHandler)
}

class SomeClass {
    var x = 10
    func doSomething() {
        someFunctionWithEscapingClosure {
            self.x = 100
        }
    }
}

let instance = SomeClass()
instance.doSomething()
completionHandlers.first?()
print(instance.x)  // Outputs 100
```

## Additional Examples

Using the `map` function with closures:

```swift
let digitNames = [0: "Zero", 1: "One", 2: "Two", 3: "Three", 4: "Four",
                  5: "Five", 6: "Six", 7: "Seven", 8: "Eight", 9: "Nine"]
let numbers = [16, 58, 510, 2127]

let numberStrings = numbers.map { (number) -> String in
    var number = number
    var output = ""
    repeat {
        output = digitNames[number % 10]! + output
        number /= 10
    } while number > 0
    return output
}
```

---

Closures are a versatile tool in Swift, allowing for concise and expressive code, especially when working with functions that take other functions as arguments, such as `map`, `filter`, and `sorted`.