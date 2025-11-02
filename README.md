# PathTracker

**PathTracker** is a lightweight, browser-based GPS walk logger designed for mobile devices. It tracks your path in real time, smooths noisy GPS data, and lets you export your walk as a GeoJSON file. Built for clarity, usability, and open-source collaboration.

## Features

- Real-time GPS tracking with smoothed position data
- Altitude, speed, bearing, and distance metrics
- Wake Lock support to prevent screen sleep during tracking
- Mobile-friendly Leaflet map interface
- Save path as `.geojson` with custom filename
- Load previously saved paths for review
- iOS/Android detection with platform-specific warnings

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
## Development

PathTracker is a single-page web app built with HTML, JavaScript, and Leaflet. It uses [GpsSmoother](https://github.com/WaltDub/GpsSmoother) for real-time position smoothing and is designed for mobile-first usability.
