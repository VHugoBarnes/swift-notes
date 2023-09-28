# Swift Error Handling

Error handling in Swift provides a structured way to handle failures in your code. Through Swift's mechanisms, you can catch, propagate, and handle errors during runtime.

## Usage of `try` and `catch`

Swift uses `throwing functions` and the `try`-`catch` syntax for error handling.

### Defining and Throwing Errors

First, you need to define an error type. Typically, you use enumerations with conforming to the `Error` protocol:

```swift
enum NetworkError: Error {
    case offline
    case serverError
    case resourceNotFound
}
```

A throwing function propagates errors using the `throw` keyword:

```swift
func fetchData() throws {
    // Some condition that leads to an error
    throw NetworkError.offline
}
```

### Catching and Handling Errors

You can use a `do`-`catch` block to catch and handle errors:

```swift
do {
    try fetchData()
} catch NetworkError.offline {
    print("No internet connection.")
} catch NetworkError.serverError {
    print("Server failed to respond.")
} catch {
    print("An unknown error occurred.")
}
```

## Assertions and Preconditions

Assertions and preconditions are checks that happen at runtime. They help you ensure that an essential condition evaluates to `true`.

### Assertions

Assertions are used during development to catch programming logic errors early:

```swift
let age = -5
assert(age >= 0, "Age cannot be a negative value")
```

If the `assert` condition is `false`, the app terminates. Assertions are generally removed from production builds.

### Preconditions

Like assertions, preconditions also check a condition but unlike assertions, preconditions remain active in production builds:

```swift
let numberOfSeats = 5
let numberOfPassengers = 6
precondition(numberOfPassengers <= numberOfSeats, "There are more passengers than seats available.")
```

If the condition provided to `precondition` evaluates to `false`, then the app will terminate, even in production.

---

By understanding Swift's error handling mechanisms, you can write robust code that gracefully handles unexpected situations and ensures certain conditions are met during runtime.