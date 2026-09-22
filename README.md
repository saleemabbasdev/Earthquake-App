# Earthquake Explorer for iOS

A SwiftUI technical exercise that loads earthquake data, presents it in a list, and displays each event on a map.

> This repository was originally created as a coding exercise. It is retained as a compact example of SwiftUI, Combine, dependency injection, networking, and unit testing.

## Highlights

- SwiftUI list, loading, error, and map experiences
- MVVM presentation architecture
- Protocol-based dependency injection
- Combine networking with `URLSession.DataTaskPublisher`
- Explicit loading, success, and failure states
- Mock JSON and a mock service for deterministic tests
- XCTest coverage for view-model behavior

## Architecture

```text
SwiftUI Views
    ↓
EarthQuakeViewModel
    ↓
EarthQuakeServiceProtocol
    ↓
EarthQuakeService / EarthQuakeMockService
    ↓
URLSession + remote earthquake API
```

The view model depends on `EarthQuakeServiceProtocol`, allowing the production service to be replaced by a mock in previews and tests.

## Project structure

- `View/` — list, earthquake row, and map screens
- `ViewModel/` — observable presentation state and loading logic
- `Networking/` — endpoint construction, API service, and error mapping
- `Model/` — decoded earthquake domain models
- `Environment/` — application dependency composition
- `Mocks/` — bundled JSON and mock service
- `eBayTestTests/` — view-model and view tests

## Requirements

- Xcode 14 or newer
- iOS 16 or newer
- Internet access for live data

## Running the project

1. Clone the repository.
2. Open `eBayTest/eBayTest.xcodeproj`.
3. Select an iPhone simulator.
4. Build and run.

No third-party dependencies are required.

## Testing

Run the test suite with **Product → Test** or press `⌘U`.

## Possible improvements

- Migrate Combine networking to Swift Concurrency
- Adopt `NavigationStack` and the modern MapKit SwiftUI API
- Replace fixed query coordinates with user-selectable regions
- Improve test synchronization without time-based delays
- Add UI and snapshot tests
- Add continuous integration

## Author

**Saleem Abbas** — Senior iOS & Mobile Engineer

- [Website](https://abbasdigital.de/)
- [LinkedIn](https://www.linkedin.com/in/saleemabbas/)
