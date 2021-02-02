## About The Project

To serve as a hands on example, this project will demenstrate the integration and usage of Graphmaster's `multiplatform-navigation` library.

## Getting Started

1. Setup artifactory credentials in the project `build.gradle` file. Credentials can be provided by Graphmasters

```
maven {
  url = "https://artifactory.graphmasters.net/artifactory/libs-release"
  credentials {
    username = "ARTIFACTORY_USERNAME"
    password = "ARTIFACTORY_PASSWORD"
    }
}
```

2. Update build config properites in the app `build.gradle`


* Replace API credentials and dedicated deployment URL
```buildConfigField "String", "NUNAV_USERNAME", "\"" + "NUNAV_USERNAME" + "\""
buildConfigField "String", "NUNAV_PASSWORD", "\"" + "NUNAV_PASSWORD" + "\""
buildConfigField "String", "NUNAV_SERVICE_URL", "\"" + "NUNAV_SERVICE_URL" + "\""
```

* For map rendering the Mapbox Android SDK is used. You can create a free account with them and create a test token.
```buildConfigField "String", "MAPBOX_TOKEN", "\"" + "MAPBOX_TOKEN" + "\""
```

## Getting Started
Once started the app requests permission to access the device location. After receiving a valid location, the camera will pan to that location.
Via long press on the map a routing destination is set and a routing session is started. Toasts will give detailed information about navigation events.
