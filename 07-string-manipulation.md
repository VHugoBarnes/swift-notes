# Swift String Manipulations

Strings in Swift are powerful and flexible, allowing you to efficiently work with text-based data. Let's delve into some aspects of string manipulation in Swift.

## Strings

In Swift, strings are represented by the `String` type. They are a series of characters, such as "hello".

```swift
let greeting = "Hello, world!"
```

## Mutability and Initialization

### Mutability

Strings can be declared as mutable (`var`) or immutable (`let`):

```swift
var mutableString = "Hello"
let immutableString = "World"
```

### Initialization

There are various ways to initialize a string:

```swift
let emptyString1 = ""
let emptyString2 = String()
```

## Characters

You can access the individual characters of a string:

```swift
for character in "Hello" {
    print(character)
}
```

## String Indexes

Strings can't be indexed by integer values. Instead, you use `String.Index`.

```swift
let word = "Swift"
let startIndex = word.startIndex
let fourthCharacter = word[word.index(startIndex, offsetBy: 3)]  // Returns 'f'
```

## Substrings

You can extract parts of a string using substring methods:

```swift
let greeting = "Hello, Swift!"
let index = greeting.firstIndex(of: ",") ?? greeting.endIndex
let beginning = greeting[..<index]  // Returns "Hello"
```

Note: Substrings share memory with the original string. For long-term storage, you might want to convert it to a `String` again.

## Prefix and Suffix

Swift provides methods to check if a string has a particular prefix or suffix:

```swift
if greeting.hasPrefix("Hello") {
    print("Begins with Hello")
}

if greeting.hasSuffix("Swift!") {
    print("Ends with Swift!")
}
```

## Unicode Representations

Strings in Swift are Unicode compliant. You can access various Unicode representations of a string:

```swift
let heart = "🩷"

for codeUnit in heart.utf8 {
    print("UTF-8: \(codeUnit)")
}

for codeUnit in heart.utf16 {
    print("UTF-16: \(codeUnit)")
}

for scalar in heart.unicodeScalars {
    print("Unicode Scalar: \(scalar.value)")
}
```

---

By understanding and using Swift's rich set of string manipulation capabilities, you can perform a wide range of tasks, from simple string manipulations to complex text processing.