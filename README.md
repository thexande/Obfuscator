# Obfuscator
A method to obfuscate strings in Swift.

[![Swift Version][swift-image]][swift-url]
[![Platform](https://img.shields.io/cocoapods/p/LFAlertController.svg?style=flat)](http://cocoapods.org/pods/LFAlertController)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

## Requirements

- iOS 9.0+
- Xcode 10

## Installation

#### CocoaPods
You can use [CocoaPods](http://cocoapods.org/) to install `Obfuscator` by adding it to your `Podfile`:

```ruby
platform :ios, '9.0'
use_frameworks!
pod 'Obfuscator'
```

To get the full benefits import `Obfuscator` wherever you import UIKit

``` swift
import UIKit
import Obfuscator
```
#### Carthage
Create a `Cartfile` that lists the framework and run `carthage update`. Follow the [instructions](https://github.com/Carthage/Carthage#if-youre-building-for-ios) to add `$(SRCROOT)/Carthage/Build/iOS/Obfuscator.framework` to an iOS project.

```
github "thexande/Obfuscator"
```
#### Manually
1. Download and drop ```Obfuscator.swift``` in your project.  
2. Congratulations!  

## Usage

1. Add the class to your project, init the object and call ` func bytesByObfuscatingString(string: String) -> [UInt8] `

```swift
final class ViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()
        let obfuscator = Obfuscator()
        print(obfuscator.bytesByObfuscatingString(string: "your_secret_string_here"))
    }
}
````

2. Retrieve your secret byte array from the console, and create a static container to hold it (`enum` to prevent init): 

```swift
enum ObfuscatedConstants {
    static let obfuscatedString: [UInt8] = [34, 17, 93, 37, 21, 28, 72, 23, 20, 22, 72, 127, 98, 123, 87, 94, 92, 83, 76, 113]
}
```

3. Call and use (example with Google Ad SDK here).

```swift
let secret = Obfuscator().reveal(key: ObfuscatedConstants.obfuscatedString)
```

4. Party 🎉

## Contribute

We would love you for the contribution to Obfuscator, check the ``LICENSE`` file for more info.

## Author

Alexander Murphy – 🐦[@thexande](https://twitter.com/thexande)

Distributed under the MIT license. See ``LICENSE`` for more information.

[swift-image]:https://img.shields.io/badge/swift-3.0-orange.svg
[swift-url]: https://swift.org/