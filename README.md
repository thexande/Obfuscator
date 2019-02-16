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
You can use [CocoaPods](http://cocoapods.org/) to install `Obfuscator` by adding it to your `Podfile` (the branch and git url won't be nessessary for long, stay tuned):

```ruby
platform :ios, '9.0'
use_frameworks!
pod 'Obfuscator', :git => 'https://github.com/thexande/Obfuscator', :tag => '1.0.0'
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