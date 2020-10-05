# Get Started

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
  - Oximeter: BW-OX1.
  - Glucometer: BW-GL1, Beurer GL 50.
  - Scale: all BT-SC series, baby scale, kitchen scale.
  - TENS: BW-TS1.
  - Pelvic TENS: BW-PFX1.
  - ECG: BW-HR1.

### Release Hitory

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
