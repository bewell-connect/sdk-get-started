# BewellConnect BluetoothLE SDK

BewellConnect BluetoothLE SDK helps integrate BewellConnect devices into iOS or Android projects without taking care of data processing.

- [BewellConnect BluetoothLE SDK](#bewellconnect-bluetoothle-sdk)
  - [BluetoothLE Android SDK](#bluetoothle-android-sdk)
    - [Compatibility](#compatibility)
    - [Release hitory](#release-hitory)
    - [Use SDK with Maven](#use-sdk-with-maven)
    - [Usage example](#usage-example)
  - [BluetoothLE iOS SDK](#bluetoothle-ios-sdk)
    - [Compatibility (iOS)](#compatibility-ios)
    - [Release hitory (iOS)](#release-hitory-ios)
    - [Use SDK with Carthage](#use-sdk-with-carthage)
    - [Usage example (iOS)](#usage-example-ios)

## BluetoothLE Android SDK

### Compatibility

- Platform
  - Android.
- Minimum SDK version
  - API 18.
- Non native dependencies used in SDK
  - [api 'com.squareup:otto:1.3.8'](https://square.github.io/otto/).
  - [api 'org.jetbrains:annotations:13.0'](https://www.jetbrains.com/help/idea/annotating-source-code.html).
- Support BLE device
  - Thermometer: BW-CX10, BW-MTX1, AOJ-20.
  - Blood Pressure monitor: BW-BW1, BW-BA*, BW-BT1.
  - Pedometer: BW-HB16, BW-M16.
  - Oximeter: BW-OX1, FS20.
  - Glucometer: BW-GL1, Beurer GL 50.
  - Scale: all BT-SC series, baby scale, kitchen scale.
  - TENS: BW-TS1.
  - Pelvic TENS: BW-PFX1.
  - ECG: BW-HR1.

### Release hitory

- 2.4.0 (02/2021)
  - ADD: compatible oximeter FS20.
- 2.3.0
  - CHANGE: migrate project to AndroidX.
- 2.2.0
  - CHNAGE: from 2.2.0, SDK will be distributed via Github Packages.
  - ADD: compatible thermometer AOJ-20.

### Use SDK with Maven

An example to use Groovy as script language:

```groovy
repositories {
  maven {
    name = "GitHubPackages"
    url = uri("https://maven.pkg.github.com/bewell-connect/ble-and-sdk-release")
    credentials {
      username = "bwc-sdk-visitor"  // keep the user name
      password = "token"  // replace with your own token, I suggest to keep the token somewhere else locally
    }
  }
}
```

make sure to use maven plugin:

```groovy
apply plugin: 'maven'
```

and add the dependency:

```groovy
implementation 'visiomed.fr:bleframework:{version}'
````

#### an example of build.gradle

```groovy
plugins {
    id 'java'
    id 'application'
    id 'maven'
}

repositories {
    google()
    jcenter()
    maven {
        name = "GitHubPackages"
        url = uri("https://maven.pkg.github.com/bewell-connect/ble-and-sdk-release")

        credentials {
            username = "bwc-sdk-visitor"
            password = "token"
        }
    }
}

dependencies {
    implementation 'visiomed.fr:bleframework:{version}'
}
```

### Usage example

clone the sample project by using the username bwc-sdk-visitor and your token:

```bash
https://github.com/bewell-connect/ble-and-demo-bis.git
```

## BluetoothLE iOS SDK

### Compatibility (iOS)

- Platform
  - iOS.
- Minimum iOS version
  - iOS 12.
- Non native dependencies used in SDK
  - N/A.
- Support BLE device
  - Thermometer: BW-CX10, BW-MTX1, AOJ-20.
  - Blood Pressure monitor: BW-BW1, BW-BA*, BW-BT1.
  - Pedometer: BW-HB16, BW-M16.
  - Oximeter: BW-OX1, FS20
  - Glucometer: BW-GL1, Beurer GL 50.
  - Scale: all BT-SC series, baby scale, kitchen scale.
  - TENS: BW-TS1.
  - Pelvic TENS: BW-PFX1.
  - ECG: BW-HR1.

### Release hitory (iOS)

- 1.8.0 (02/2021)
  - ADD: compatible oximeter FS20.
- 1.7.1
  - FIX: several bugs when copy THERMO_AOJ20 or TemperatureData's object.
- 1.7.0
  - ADD: compatible thermometer AOJ-20.

### Use SDK with Carthage

Create a Cartfile in the project root:

```bash
github "bewell-connect/ble-ios-sdk-release"
```

run command in project root:

```bash
carthage update --platform ios --no-build
```

will create a Carthage folder in the project root, find the "Checkouts" folder and unzip the "Build" folder into Carthage folder as it is in the zip file, then you can find the framework in the "Build" folder which you can integrate as embered framework into your project.

### Usage example (iOS)

clone the sample project by using the username bwc-sdk-visitor and your token:

```bash
https://github.com/bewell-connect/ble-and-demo-bis.git
```
