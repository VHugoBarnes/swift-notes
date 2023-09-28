# Swift Data Structures

Swift provides powerful built-in data structures to organize and store values. This document covers arrays, sets, and dictionaries, along with their common operations.

## Arrays

Arrays are ordered collections of values. They can contain multiple values of the same type.

### Declaration and Initialization:

```swift
var numbers: [Int] = [1, 2, 3, 4]
let fruits: [String] = ["apple", "banana", "cherry"]
```

### Access and Modify Elements in an Array:

You can access and modify elements using their index:

```swift
let firstNumber = numbers[0]  // Returns 1
numbers[1] = 5                // Changes the second element to 5
```

Add and remove elements:

```swift
numbers.append(6)             // Adds 6 to the end
numbers.remove(at: 2)        // Removes the third element
```

### Iterating an Array:

```swift
for number in numbers {
    print(number)
}

for (index, value) in numbers.enumerated() {
    print("Item \(index): \(value)")
}
```

## Sets

Sets are unordered collections of unique values.

### Declaration and Initialization:

```swift
var letters: Set<Character> = ["a", "b", "c"]
let colors: Set<String> = ["red", "green", "blue"]
```

### Iterations and Operations on a Set:

Iterate over a set:

```swift
for letter in letters {
    print(letter)
}
```

Common set operations:

```swift
let oddNumbers: Set = [1, 3, 5, 7]
let evenNumbers: Set = [2, 4, 6, 8]

let allNumbers = oddNumbers.union(evenNumbers)
let commonNumbers = oddNumbers.intersection(evenNumbers)
```

## Dictionaries

Dictionaries store associations between keys of the same type and values of the same type.

### Declaration and Initialization:

```swift
var namesOfIntegers: [Int: String] = [1: "one", 2: "two"]
let capitals: [String: String] = ["France": "Paris", "Italy": "Rome"]
```

### Iteration on Dictionaries:

```swift
for (country, capital) in capitals {
    print("\(country)'s capital is \(capital)")
}

for country in capitals.keys {
    print(country)
}

for capital in capitals.values {
    print(capital)
}
```

---

Understanding and efficiently using these data structures can help you store and manage data more effectively in your Swift applications.