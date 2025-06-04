# BGrund
Research and Templates for Background Services in Android Applications

**BGrund** is an Android application demonstrating a persistent Foreground Service that tracks the user's location, monitors device sensors, periodically sends data to a remote server via API calls, and continues running in the background. The service automatically restarts upon termination or device reboot.

## Features

- **Foreground Service:** Continuously tracks GPS location and accelerometer data.
- **Periodic API Calls:** Sends sensor and location data to a remote server every 60 seconds.
- **Automatic Restart:** Automatically restarts if terminated or after a device reboot.
- **User Interface:** Provides a simple interface with a button to toggle the service and a timer indicating how long the service has been active.

## Compatibility

- Minimum Android API: **21 (Lollipop)**
- Target Android API: **33 (Android 13)**

## Project Structure

The repository contains a single Android application module located in the `app/` directory. The important parts of the module are:

- **`app/src/main/java`** – Java source files.
  - `MainActivity.java` – user interface and interaction logic.
  - `BackgroundService.java` – minimal foreground service implementation.
- **`app/src/main/res`** – XML resources such as layouts and strings (`activity_main.xml`, etc.).
- **`app/src/main/AndroidManifest.xml`** – application manifest and permission configuration.

## Permissions

The app requests the following permissions:

- `ACCESS_FINE_LOCATION`
- `ACCESS_BACKGROUND_LOCATION`
- `ACTIVITY_RECOGNITION`
- `FOREGROUND_SERVICE`
- `POST_NOTIFICATIONS`
- `INTERNET`

## How to Build and Deploy

1. Clone the repository.
   ```sh
   git clone <repository_url>
   ```
2. Open the project in Android Studio and allow Gradle to sync all dependencies.
3. Click **Run** to build and launch the application on a connected emulator or Android device.
4. To produce an APK select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Install the generated APK via Android Studio or from the command line:
   ```sh
   adb install app/build/outputs/apk/debug/app-debug.apk
   ```

## Usage

- Launch the app.
- Grant all necessary runtime permissions when prompted.
- Use the **Start Service** button to initiate tracking.
- The timer displays how long the service has been running.
- To stop the service, press the **Stop Service** button.

## API Integration

Update the API endpoint URL in `BackgroundService.java` (`sendDataToServer()` method) to your server's URL:

```java
URL url = new URL("https://your-server.com/api/endpoint");
```

## Contributing

Contributions are welcome. Please open an issue or submit a pull request for improvements or new features.

## License

Distributed under the MIT License. See `LICENSE` for more information.


## Example Implementation

The `app` module contains a minimal example targeting Android 24+ with a simple foreground service that runs in the background. Open the project in Android Studio to build and run the sample.
