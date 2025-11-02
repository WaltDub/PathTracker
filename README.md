# PathTracker

**PathTracker** is a lightweight, browser-based GPS walk logger designed for mobile devices. It tracks your path in real time, smooths noisy GPS data, and lets you export your walk as a GeoJSON file. Built for clarity, usability, and open-source collaboration.

## Support This Project
If you find PathTracker useful, consider supporting its development:

[![Donate via Stripe](https://img.shields.io/badge/Donate-Stripe-blue)](https://donate.stripe.com/7sYbJ2de5eHX4gO5BZbbG00)

## Features

Each feature in **PathTracker** is designed for clarity, usability, and real-world GPS logging on mobile devices:

**Real-time GPS tracking with smoothed telemetry**  
Uses `navigator.geolocation.watchPosition()` combined with [GpsSmoother](https://github.com/WaltDub/GpsSmoother) to capture and refine location data.  
Ensures accurate, jitter-free traces even in urban or forested environments.

**Altitude, speed, and bearing display**  
Calculates smoothed metrics using haversine distance and vector math.  
Provides meaningful feedback for hikers, runners, and directional navigation.


**Wake Lock support to prevent screen sleep**  
Leverages the Wake Lock API to keep the screen awake during tracking.  
Prevents data gaps caused by browser suspension when the device sleeps — critical for uninterrupted logging.

**Platform detection with user guidance**  
Detects iOS vs Android and displays warnings when Wake Lock is unsupported.  
Improves reliability by informing users of platform-specific limitations and workarounds.

**Mobile-friendly Leaflet map interface**  
Displays live position and path using Leaflet.js with OpenStreetMap tiles.  
Offers intuitive, responsive visualization optimized for small screens and touch input.

**GeoJSON export with custom filename**  
Generates a standards-compliant `.geojson` file containing coordinates and metadata.  
Supports direct import into GIS tools, mapping platforms, and spatial databases.

**File import for reviewing saved paths**  
Allows users to load previously saved GeoJSON files and visualize them on the map.  
Enables comparison, review, and reuse of past walks without external tools.

**Stateless, single-file architecture**  
Implements all logic in a standalone HTML file with no build tools or dependencies.  
Easy to host, fork, and customize — ideal for open-source distribution and educational use.

## Demo

Try it live: [https://waltdub.github.io/PathTracker](https://waltdub.github.io/PathTracker)

## Usage

1. Open the app in a mobile browser with GPS enabled
2. Press **Start** to begin tracking your walk
3. Press **Stop** to end tracking
4. Press **Save Path** to download your walk as a GeoJSON file
5. Press **Load Path** to import and view a previously saved trace

> On iOS, screen sleep may interrupt tracking. Consider disabling Auto-Lock in Settings.

## File Format

Saved paths use the [GeoJSON](https://geojson.org/) format:

```json
{
  "type": "FeatureCollection",
  "features": [{
    "type": "Feature",
    "geometry": {
      "type": "LineString",
      "coordinates": [[lon, lat], ...]
    },
    "properties": {
      "name": "PathTracker walk trace",
      "distance_m": 1234,
      "min_altitude_m": 12.3,
      "max_altitude_m": 45.6
    }
  }]
}
```
## Use Cases

PathTracker is designed for real-world GPS logging across a variety of scenarios:

- **Hiking and trail exploration**  
  Track your route, elevation changes, and distance walked in remote areas.

- **Urban walking and sightseeing**  
  Log city walks, tourist routes, or neighborhood strolls with accurate path data.

- **Fitness and training**  
  Monitor speed, altitude, and distance during runs or workouts.

- **Vehicle movement tracking**  
  Record driving paths for delivery routes, fieldwork, or compliance checks.

- **GeoJSON-based mapping projects**  
  Export standardized path data for use in Leaflet, Mapbox, or GIS platforms.

- **Mobile-friendly field logging**  
  Use directly in the browser without installing apps — ideal for quick deployment.

- **Testing GPS smoothing algorithms**  
  Compare raw vs. smoothed telemetry for research, debugging, or algorithm tuning.

- **Direction and bearing analysis**  
  Visualize heading changes and movement stability over time.

---

## License

This project is licensed under the **MIT License**
