# Swift Implementation of the LIFX Binary Protocol

This is the Swift implementation of the LIFX Binary Protocol, and supports serialising and deserialising all supported message types.

### Using This Library
The Messages class has simple tools for deserializing data received via the LAN.

The following code reads in LIFX messages from the given `Data` and wraps those messages in an enum. The `DeviceMessage` enum is the recommended way of creating a message handler as it allows for a type-safe way of ensuring you can process all types of LIFX messages you may receive.
```swift
let messages = Messages.read(data: data)
let wrapped = messages.map { Messages.deviceMessage(for: $0) }
```

### Protocol Documentation
Full documentation for the LIFX Protocol can be found on the [LIFX Developer site](https://lan.developer.lifx.com/docs). 

### Using with Xcode
Just open the swift folder with Xcode 11 or later and it will be handled as a SwiftPM project. The library also supports CocoaPods.
