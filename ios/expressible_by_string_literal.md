## ExpressibleByStringLiteral

It is a protocol in Swift 3 (which was StringLiteralConvertible in Swift 2). The name clearly reflects the meaning that an object of a class can be expressed by a literal string.

```
let person: Person = "Thuyen"	// Instead of: let person = Person(name: "Thuyen")
```
To use it, the class must conform to `ExpressibleByStringLiteral`:

```
final class Person: ExpressibleByStringLiteral {
	var name: String = ""

	init(stringLiteral value: String) {
        self.name = value
    }
    
    init(extendedGraphemeClusterLiteral value: String) {
        self.name = value
    }
    
    init(unicodeScalarLiteral value: String) {
        self.name = value
    }
}

let person: Person = "Thuyen"
```

A few examples in which we could use ExpressibleByStringLiteral:
```
let timezone: TimeZone = "GMT+03:00"
let date: Date = "2016-12-03T00:40:11+00:00"
let url: URL = "https://google.com"
let coordinate: Coordinate = "123.5, 127.8"
```

And, we have some more similar protocols: `ExpressibleByArrayLiteral, ExpressibleByNilLiteral, ExpressibleByIntegerLiteral, ExpressibleByFloatLiteral, ExpressibleByBooleanLiteral, ExpressibleByDictionaryLiteral`.

p/s: Not until now do I know this protocol. Kind of late :))

