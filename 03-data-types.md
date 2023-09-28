# Swift Data Types

Swift offers a rich set of both built-in and custom data types.

## Integers

Integers are whole numbers without a fractional component. Swift offers several kinds of integers, both signed (with positive and negative values) and unsigned (positive values only).

**Example**:
```swift
let age: Int = 25
let population: UInt = 300_000
let minValue = UInt8.min // 0
let maxValue = UInt8.max // 255
```

## Floats and Doubles

`Float` and `Double` represent real numbers with fractional components. `Float` represents a 32-bit floating-point number, while `Double` represents a 64-bit floating-point number.

**Example**:
```swift
let pi: Float = 3.14593
let gravity: Double = 9.810000000
```

## Numeric Literals

You can write numeric literals in Swift using different notations — decimal, binary, octal, or hexadecimal.

**Example**:
```swift
let decimal = 42
let binary = 0b101010
let octal = 0o52
let hexadecimal = 0x2A
```

## Cast Between Types

You can convert between numeric types by initializing a new instance of the desired type.

**Example**:
```swift
let intVal: Int = 42
let doubleVal = Double(intVal)
let floatVal: Float = Float(intVal)
```

## TypeAlias (Nicknames for Datatypes)

Use `typealias` to provide a new name for an existing type. It's like creating a nickname.

**Example**:
```swift
typealias Distance = Double
let marathon: Distance = 42.195
```

## Booleans

Booleans represent true or false values.

**Example**:
```swift
let isSunny: Bool = true
let isRainy = false
```

## Tuples

Tuples group multiple values into a single compound value. The values within a tuple can be of any type.

**Example**:
```swift
let httpStatus = (statusCode: 200, description: "OK")
print(httpStatus.statusCode)  // Outputs: 200
```

## Optionals and Nil

An optional in Swift represents a variable that can hold either a value or no value (nil).

**Example**:
```swift
var name: String?  // This is an optional string
name = "Steve"
name = nil         // Now it's nil
```

To check if an optional contains a value, you can use the optional binding method or the `nil` coalescing operator.