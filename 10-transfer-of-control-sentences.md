# Swift Transfer Control Statements

Swift provides several control transfer statements to manage the flow of execution in your code. They help in altering the default sequence of operations.

## Continue and Break

### Continue:

The `continue` statement tells a loop to stop what it's doing and start again at the beginning of the next iteration.

```swift
for number in 1...5 {
    if number == 3 {
        continue
    }
    print(number)
}
```

### Break:

The `break` statement ends the execution of an entire control flow statement immediately.

```swift
for number in 1...10 {
    if number == 6 {
        break
    }
    print(number)
}
```

## Fallthrough

In Swift, `switch` statements don’t fall through the bottom of each case and into the next one by default. If you need this behavior, use the `fallthrough` keyword.

```swift
let integerToDescribe = 5
var description = "The number \(integerToDescribe) is"
switch integerToDescribe {
case 2, 3, 5, 7, 11, 13, 17, 19:
    description += " a prime number, and also"
    fallthrough
default:
    description += " an integer."
}
print(description)
```

## Return and Guard

### Return:

The `return` statement is used to return from a function before the end of the function is reached.

```swift
func greet(person: String) -> String {
    if person == "Enemy" {
        return "No greetings for you!"
    }
    return "Hello, \(person)!"
}
```

### Guard:

The `guard` keyword is a powerful feature in Swift that provides an early exit from the function, loop, or condition where it's used. It allows for a cleaner syntax in scenarios where conditions must be met for the function or method to proceed correctly.

0. **Basic usage**:

    ```swift
    func greetIfAdult(age: Int) {
        guard age >= 18 else {
            print("You're too young!")
            return
        }
        print("Greetings!")
    }
    ```

1. **Checking Optionals**:

    ```swift
    func greet(person: [String: String]) {
        guard let name = person["name"] else {
            print("Name not found!")
            return
        }
        print("Hello, \(name)!")
    }
    ```

2. **Multiple Conditions**:

    In scenarios where multiple conditions need to be satisfied, you can use multiple `guard` clauses:

    ```swift
    func processFile(name: String?, size: Int?) {
        guard let fileName = name, let fileSize = size, fileSize < 1000 else {
            print("Invalid file or file too large.")
            return
        }
        print("Processing \(fileName) of size \(fileSize)KB")
    }
    ```

3. **Combining with `let` and `where`**:

    The `guard` statement can be combined with `let` for optional binding and `where` for additional conditions:

    ```swift
    func validate(input: [String: Any]) {
        guard let age = input["age"] as? Int, age >= 18, let country = input["country"] as? String, country == "US" where age >= 21 else {
            print("Criteria not met!")
            return
        }
        print("Criteria met!")
    }
    ```

4. **In Loops**:

    `guard` can be used inside loops to skip iterations:

    ```swift
    let items = ["apple", "42", "banana", "100"]
    for item in items {
        guard let number = Int(item) else {
            continue  // Skip to the next iteration if item isn't a number
        }
        print("Found number: \(number)")
    }
    ```

5. **In Network Calls**:

    The `guard` statement is particularly useful in handling early returns, especially in scenarios like network calls:

    ```swift
    func fetchData(completion: (String?, Error?) -> Void) {
        let data: String? = "...fetched data..."
        let error: Error? = nil
        
        guard error == nil else {
            completion(nil, error)
            return
        }
        
        guard let validData = data else {
            completion(nil, MyError.dataInvalid)
            return
        }
        
        completion(validData, nil)
    }
    ```

The `guard` statement enhances code readability by reducing the nested depth of `if` statements and by ensuring certain conditions are met before the function proceeds further.

## #available API

The `#available` condition checks the API availability on the runtime's OS version.

```swift
if #available(iOS 10, macOS 10.12, *) {
    // Use APIs available in iOS 10 and macOS 10.12 and newer
} else {
    // Fallback on earlier versions
}
```

---

With Swift's control transfer statements, you can create more flexible and efficient code that behaves exactly as needed in various situations.