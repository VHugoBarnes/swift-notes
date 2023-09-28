# Swift Enumerations

Enumerations in Swift are a powerful way to define a common type for a group of related values. They enable you to work with those values in a type-safe way within your code.

## Enums

Basic enumeration definition:

```swift
enum SomeEnumeration {
    // Here goes the enumeration definition
}
```

```swift
enum CompassPoint: String {
    case north
    case south
    case east
    case west
}
```

## Raw Values

Enums can be given raw values which are all of the same type:

```swift
enum Planet: Int {
    case mercury = 1, venus, earth, mars, jupiter, saturn, uranus, neptune
} // earth == 3
```

### Examples:

Assigning an enum case:

```swift
var directionToGo = CompassPoint.east
directionToGo = .south
```

Using a switch statement with enums:

```swift
switch directionToGo {
case .north:
    print("Go north")
case .south:
    print("There are penguins in the south")
case .east:
    print("Mordor stretches to the eastlands")
case .west:
    print("Watch out for cowboys")
}
```

A more complex example:

```swift
enum Barcode {
    case upc(Int, Int, Int, Int)
    case qrCode(String)
}

var productBarcode = Barcode.upc(8, 85909, 51226, 3)
productBarcode = .qrCode("ASDFGHJKL")

switch productBarcode {
case let .upc(numberSystem, manufacturer, product, check):
    print("UPC: \(numberSystem), \(manufacturer), \(product), \(check).")
case let .qrCode(productCode):
    print("QR: \(productCode)")
}
```

Enumerations with character raw values:

```swift
enum ASCIIControlCharacter: Character {
    case tab = "\t"
    case lineFeed = "\n"
    case carriageReturn = "\r"
}
```

Using raw values:

```swift
let earthOrder = Planet.earth.rawValue // earth
let northDirection = CompassPoint.north.rawValue // north
let possiblePlanet = Planet(rawValue: 5) // jupiter
```

Handling possible enum values using `rawValue`:

```swift
let planetPosition = 3
if let anyPlanet = Planet(rawValue: planetPosition) {
    switch anyPlanet {
    case .earth:
        print("Earth is safe")
    default:
        print("It's not safe to go to this planet")
    }
} else {
    print("The indicated planet doesn't exist...")
}
```

---

Enumerations are a powerful feature in Swift, allowing for a clear and expressive way to represent a group of related values with associated raw values or associated data.