# Swift Conditionals and Basic Operations

Swift offers a plethora of operators that allow for various conditional checks and basic operations. Let's delve into them.

## Assignment and Arithmetic Operations

### Assignment (`=`)

It assigns the value on its right to the variable on its left.

```swift
let name = "John"
```

### Arithmetic Operations

- **Addition** (`+`): `let sum = 3 + 2`
- **Subtraction** (`-`): `let difference = 5 - 3`
- **Multiplication** (`*`): `let product = 4 * 3`
- **Division** (`/`): `let quotient = 8 / 2`
- **Remainder** (`%`): `let remainder = 9 % 4`

## Comparisons

Swift supports all standard comparison operations:

- **Equal** (`==`): `if age == 30 { ... }`
- **Not Equal** (`!=`): `if age != 30 { ... }`
- **Greater Than** (`>`): `if age > 21 { ... }`
- **Less Than** (`<`): `if age < 21 { ... }`
- **Greater Than or Equal** (`>=`): `if age >= 18 { ... }`
- **Less Than or Equal** (`<=`): `if age <= 18 { ... }`

## Ternary Operations (`? :`)

It's a shorthand for evaluating one of two expressions based on a condition.

```swift
let accessGranted = (age >= 18) ? "Access granted" : "Access denied"
```

## Nil Coalescing Operator (`??`)

It provides a default value for optional variables.

```swift
let defaultName = "Guest"
let providedName: String? = nil
let username = providedName ?? defaultName  // username will be "Guest"
```

## Ranges

- **Closed Range** (`...`): Represents a range that includes both its start and end value. Example: `1...5` includes numbers 1, 2, 3, 4, and 5.
  
- **Half-Open Range** (`..<`): Represents a range that includes its start value but excludes its end value. Example: `1..<5` includes numbers 1, 2, 3, and 4.

## Logic Operators

- **Logical NOT** (`!`): Inverts a Boolean value. Example: `let isClosed = !isOpen`
  
- **Logical AND** (`&&`): Returns `true` if both conditions are `true`. Example: `if isHungry && hasFood { ... }`
  
- **Logical OR** (`||`): Returns `true` if at least one of the conditions is `true`. Example: `if isRaining || hasUmbrella { ... }`

---

By understanding Swift's conditionals and basic operations, you can perform a wide range of tasks, from simple arithmetic to complex conditional checks.