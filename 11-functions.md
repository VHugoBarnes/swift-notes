# Swift Functions

Functions are fundamental building blocks in Swift, allowing for modular, reusable code. This guide explores various aspects of declaring and using functions in Swift.

## Declaring Functions

A simple function declaration consists of the `func` keyword, the function's name, and its body:

```swift
func greet() {
    print("Hello, world!")
}
```

## Input Parameters

Functions can take multiple input parameters:

```swift
func greet(name: String, age: Int) {
    print("Hello, \(name)! You are \(age) years old.")
}
```

## Return Values, Optionals, and Output Params

### Return Values:

A function can return a value using the `->` notation:

```swift
func add(a: Int, b: Int) -> Int {
    return a + b
}
```

### Optionals:

Functions can return optional values, indicating the possibility of returning `nil`:

```swift
func findAge(name: String) -> Int? {
    if name == "Alice" {
        return 30
    }
    return nil
}
```

### Output Parameters:

You can use output parameters to get values out of the function, but they're less common in Swift:

```swift
func modify(value: Int, modifiedValue: inout Int) {
    modifiedValue = value * 2
}
```

## Parameter Labels and Variadics

### Parameter Labels:

Swift allows function parameters to have a distinct external name and an internal name:

```swift
func greet(person name: String, from hometown: String) {
    print("Hello \(name)! Glad you're from \(hometown).")
}
```

### Variadics:

Variadic parameters allow you to send multiple values for a specific parameter:

```swift
func printNumbers(numbers: Int...) {
    for number in numbers {
        print(number)
    }
}
```

## Inout Parameters

Parameters are constants by default. If you want a function to modify a parameter and persist those changes outside the function's body, use the `inout` keyword:

```swift
func doubleInPlace(value: inout Int) {
    value *= 2
}
```

## Function Types

Every function has a type, comprising its parameter types and return type:

```swift
let addFunction: (Int, Int) -> Int = add
```

## Nested Functions

Functions can be nested inside other functions:

```swift
func printIncrementedValues(_ values: [Int]) {
    func increment(value: Int) -> Int {
        return value + 1
    }
    
    for value in values {
        print(increment(value: value))
    }
}
```

---

By understanding and utilizing the rich functionality associated with Swift's functions, you can create flexible, reusable, and concise code pieces.