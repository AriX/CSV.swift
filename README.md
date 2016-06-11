# CSV.swift

CSV reading library written in Swift.

## Usage

### From CSV string

```swift
import CSV

let csvString = "1,\"foo\"\n2,\"bar\""
for row in try! CSV(string: csvString) {
    print("\(row)")
    // => ["1", "foo"]
    // => ["2", "bar"]
}
```

### From file path

```swift
import CSV

for row in try! CSV(path: "/path/to/file.csv") {
    print("\(row)")
}
```

### Getting the header row

```swift
let csv = try! CSV(
    path: "/path/to/file.csv",
    hasHeaderRow: true) // default: false

let headerRow = csv.headerRow!

for row in csv {
    // ...
}
```

### Provide the character encoding

If you use a file path, you can provide the character encoding to initializer.

```swift
let csv = try! CSV(
    path: "/path/to/file.csv",
    encoding: NSUTF8StringEncoding)
```

## Installation

### CocoaPods

```ruby
pod 'CSV.swift', '~> 0.1'
```

### Carthage

```
github "yaslab/CSV.swift" ~> 0.1
```

### Swift Package Manager

```swift
import PackageDescription

let package = Package(
    name: "PackageName",
    dependencies: [
        .Package(url: "https://github.com/yaslab/CSV.swift", majorVersion: 0, minor: 1)
    ]
)
```

## License

CSV.swift is released under the MIT license. See the LICENSE file for more info.
