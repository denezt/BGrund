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

- **`MainActivity.java`**: UI and interaction logic.
- **`BackgroundService.java`**: Implements the foreground service, location tracking, sensor monitoring, and API interaction.
- **`RestartServiceReceiver.java`**: Handles service restart logic on boot or unexpected termination.
- **Layout XML**: Defines UI layout (`activity_main.xml`).
- **`AndroidManifest.xml`**: Configures permissions, service, and broadcast receivers.

## Permissions

The app requests the following permissions:

- `ACCESS_FINE_LOCATION`
- `ACCESS_BACKGROUND_LOCATION`
- `ACTIVITY_RECOGNITION`
- `FOREGROUND_SERVICE`
- `POST_NOTIFICATIONS`
- `INTERNET`

## How to Build

1. Clone the repository.
   ```sh
   git clone <repository_url>
   ```
2. Open the project in Android Studio.
3. Allow Gradle to sync dependencies.
4. Build and run the application on an emulator or physical Android device.

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

