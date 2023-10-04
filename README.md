[![Swift Version](https://img.shields.io/badge/Swift-5.9-green.svg)](https://swift.org) ![example event parameter](https://github.com/emvakar/EKAstrologyCalc/actions/workflows/tests.yml/badge.svg?branch=master)

# Astrology Calculator
This is Moon Calc Framework written on Swift
Get moon phase by Date and Location

## What we can do right now:

- [x] set and rise moon
- [x] get moon Age
- [x] get moon rise
- [x] get moon set
- [x] get zodiac sign
- [x] get moon phase
- [x] get moon trajectory
- [x] get moon illumination
- [ ] get moon rise if rise on past date
- [ ] get moon set if set on future date
- [ ] get zodiac sign rise time
- [ ] get zodiac sign set time
- [ ] get mercury status and times
- [x] get eclipse times (begin, duration, finish)
- [ ] create UI for calendar

### Support EKAstrologyCalc development by giving a ⭐️

## Installation

### via Swift Package Manager

```swift
    .package(url: "https://github.com/emvakar/EKAstrologyCalc.git", from: "1.0.4")
```

## Usage

```swift
import UIKit
import CoreLocation
import EKAstrologyCalc

class ViewController: UIViewController {

    let location = CLLocation(latitude: 55.751244, longitude: 37.618423) // Moscow
    var moonPhaseManager: EKAstrologyCalc!

    override func viewDidLoad() {
        super.viewDidLoad()
        
        moonPhaseManager = EKAstrologyCalc(location: location)

        let info = moonPhaseManager.getInfo(date: Date())

        print("Current localtion: -", info.location.coordinate)

        print("Moon days at", "current date: -", info.date)
        info.moonModels.forEach {
            print("===========")
            print("Moon Age: -", $0.age)
            print("Moon rise: -", $0.moonRise)
            print("Moon set: -", $0.moonSet)
        }
        print("===========")
        print("Moon phase: -", info.phase)
        print("Moon trajectory: -", info.trajectory)
    }
}
```
