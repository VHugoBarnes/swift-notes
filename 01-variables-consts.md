# Variables and Constants in Swift

## `var` and `let`

In Swift, you use `var` to declare a variable, which means its value can be changed after it's set. On the other hand, you use `let` to declare a constant, which means its value cannot be changed once it's set.

**Example**:
```swift
let maximumNumberOfLoginAttempts = 3  // This is a constant
var currentLoginAttempt = 0           // This is a variable

var x = 0.0, y = 0.0, z = 0.0         // Declaring multiple variables on a single line
```

## Type Annotations
Swift provides a powerful type inference system. But if you want to specify the type of the variable or constant explicitly, you can provide a type annotation.

**Example**:
```swift
var welcomeMessage: String            // The type of variable is explicitly set to String
welcomeMessage = "Hello"

var red, green, blue: Double          // All these variables are explicitly set to type Double
```

## Nomenclature for Naming Variables
In Swift, it's a common practice to name variables in a camelCase manner.

**Good Practices**:
```swift
var userName: String
let maximumSpeed: Double
```

**Not Recommended**:
```swift
var username: String     // not very readable when multiple words are squashed together
let MaximumSpeed: Double // constants should not start with a capital letter
```

## The print Function
The print function in Swift is used to display the output of the provided parameters to the console.

**Example**:
```swift
let greeting = "Hello, World!"
print(greeting)            // Outputs: Hello, World!
```

## Comments in Swift Code
Comments are used to annotate the code with helpful descriptions so that it becomes easier to read and understand.

**Example**:
```swift
// This is a single line comment

/* 
   This is a 
   multiline comment.
*/

/// This is a documentation comment. It's often used to describe interfaces.
func sum(a: Int, b: Int) -> Int {
    return a + b
}
```

Remember, writing clean, well-commented code can help others understand your intent and make collaborative efforts smoother.