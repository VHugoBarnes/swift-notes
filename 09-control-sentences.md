# Swift Control Statements

Control statements in Swift allow for efficient code execution flow management. This document covers the various control statements provided by Swift.

## For-In Loop

The `for-in` loop iterates over a sequence, such as an array, dictionary, or a range.

### Example:

```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}

let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names {
    print(name)
}
```

## While / Repeat-While

The `while` loop evaluates its condition at the start, and the `repeat-while` loop evaluates its condition at the end.

### Example:

```swift
var i = 1
while i < 5 {
    print(i)
    i += 1
}

var j = 1
repeat {
    print(j)
    j += 1
} while j < 5
```

## If

The `if` statement is used to conditionally execute a set of statements.

### Example:

```swift
let temperature = 22
if temperature < 20 {
    print("It's cold!")
} else if temperature > 30 {
    print("It's hot!")
} else {
    print("It's moderate!")
}
```

## Switch

The `switch` statement compares a value against multiple possible matching patterns.

### Ranges in Switch (Interval Matching):

```swift
let count = 3
switch count {
case 1...5:
    print("There are a few items.")
default:
    print("There are many items.")
}
```

### Tuples in Switch:

```swift
let coordinate = (1, 3)
switch coordinate {
case (0, 0):
    print("Origin")
case (_, 0):
    print("On the x-axis.")
case (0, _):
    print("On the y-axis.")
case (-2...2, -2...2):
    print("Inside the 2x2 box.")
default:
    print("Outside the box.")
}
```

### Compound Cases in Switch:

```swift
let character: Character = "e"
switch character {
case "a", "e", "i", "o", "u":
    print("\(character) is a vowel")
default:
    print("\(character) is a consonant")
}
```

---

By understanding and using Swift's control statements, you can efficiently manage the flow of code execution in your applications.