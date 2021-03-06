![pulse-small](https://user-images.githubusercontent.com/1567433/80981674-4b1fc300-8df8-11ea-9732-94388f0473ae.jpg)

<p align="left">
<img src="https://img.shields.io/badge/platforms-iOS%2C%20macOS%2C%20watchOS%2C%20tvOS-lightgrey.svg">
<img src="https://github.com/kean/Pulse/workflows/CI/badge.svg">
</p>

**Pulse** is a logging system with structured persistent storage.

**PulseUI** allows you to quickly preview logs in your iOS or tvOS apps. Share logs, and use Pulse macOS app to search and filter them. **PulseUI** is available for [**GitHub sponsors**](https://github.com/sponsors/kean).

<br/>

# Usage

Use `log()` function to send logs.

```swift
log("Your message")
log(level: .fatal, system: .auth, "Configuration is missing")
```

```swift
/// Logs the message in the console (if enabled) and saves it persistently.
///
/// - note: Logger automatically captures stack traces for .fatal logs.
///
public func log(level: Logger.Level = .debug,
                system: Logger.System = .default,
                category: Logger.Category = .default,
                _ text: @autoclosure () -> String)
```

All of the logged messages are stored persistently using Core Data. You get full access to all of the recorded messages at any time using `Logger.Store`.

```swift
let message = try logger.store.allMessage()

// NSPersistentStoreContainer
let container = logger.store.container
```

<br/>

# PulseUI

**PulseUI** allows you to quickly preview logs in your iOS or tvOS apps. Share logs, and use Pulse macOS app to search and filter them. **PulseUI** is available for [**GitHub sponsors**](https://github.com/sponsors/kean).

<br/>

### iOS Console

Build a console right into your iOS apps.

<img width="320" alt="Screen Shot 2020-05-04 at 13 50 26" src="https://user-images.githubusercontent.com/1567433/80996719-4960fa00-8e0e-11ea-909a-9ff80f49382e.png"> <img width="320" alt="Screen Shot 2020-05-04 at 10 43 28" src="https://user-images.githubusercontent.com/1567433/80979399-49083500-8df5-11ea-8313-54841b86777c.png">

<br/>

### macOS App

Share your Pulse database and view it on your Mac. Use advanced search to filter your messages.

<img width="706" alt="Screen Shot 2020-05-05 at 10 47 53" src="https://user-images.githubusercontent.com/1567433/81079719-e4fd7380-8ebd-11ea-89f6-4913528c1738.png">


# Minimum Requirements

| Nuke          | Swift           | Xcode           | Platforms                                         |
|---------------|-----------------|-----------------|---------------------------------------------------|
| Pulse 0.3      | Swift 5.2       | Xcode 11.3      | iOS 11.0 / watchOS 4.0 / macOS 10.13 / tvOS 11.0  |

# License

Pulse is available under the MIT license. See the LICENSE file for more info.

