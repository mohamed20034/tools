# Mohsen Tools — World Time & Meeting Planner

A standalone, responsive world-clock and international meeting planner. Built as a static web app with no build step or API key.

## Features

### World clock
- Search by city, street address, ZIP code or postal code.
- Select among geocoding matches; resolve coordinates to an IANA time zone.
- Add up to 10 cities to a live, side-by-side world clock.
- 12/24-hour display, local dates, UTC offsets and difference from Egypt.
- Save favorites and recent searches in the browser.
- Use browser geolocation with permission.
- Share a link containing your selected city setup.
- Quick browser of popular global business hubs.

### Time conversion
- Convert a selected local date and time between IANA time zones.
- Apply date-specific daylight-saving offsets using the browser's Intl time-zone database.
- Show source and target offsets and compare historical/future offsets around the selected date.
- Export a converted appointment as an .ics calendar event.

### Meeting planning
- Set working hours, date, duration and attendees from your saved locations.
- Find half-hour start times where all selected cities are within the configured working hours.
- View a 24-hour working-hours timeline.
- Find the next practical local time to call a recipient.
- Preview the next six weekly recurring meeting occurrences in every saved city.
- Export those six occurrences as a multi-event .ics calendar file.

### Map and daylight
- Interactive OpenStreetMap map with saved and popular-city markers.
- View local sunrise, sunset and a day/night indicator.
- Compare current UTC offset with the offset 180 days ahead for seasonal/DST change alerts.

### Installability
- Web app manifest and service worker for installable PWA behavior.
- The app shell is cached for basic offline loading. Geocoding, time-zone lookup, map tiles and sunrise/sunset data still require an internet connection.

## Deploy with GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, select **Deploy from a branch**.
3. Select branch **main** and folder **/(root)**, then Save.
4. Wait for GitHub Pages to publish the site.

The expected URL is:

https://mohamed20034.github.io/tools/

## Data sources and limitations

- **Photon / OpenStreetMap** provides address and postal-code geocoding.
- **Hourora API** maps searched coordinates to a time-zone identifier using its nearest-city dataset. This may be approximate near time-zone borders or remote locations.
- **Browser Intl / IANA time-zone data** formats clocks and performs date-aware UTC-offset calculations.
- **Open-Meteo** provides sunrise and sunset times.
- **Leaflet + OpenStreetMap** provide the interactive map.

Meeting overlap is calculated in 30-minute increments using the selected workday window and each city's local time. It is a planning aid, not a guarantee of participant availability. DST transitions can make some local wall-clock times ambiguous or nonexistent; verify critical meetings.
The DST alert compares the current UTC offset with the offset 180 days later. It indicates a likely seasonal offset change but does not claim to report the exact transition date.
Geolocation is only accessed after the user presses the location button and grants browser permission. Favorites and recent searches are stored locally in the browser. Share links include selected city names, coordinates and time zones in the URL.

## Run locally

Serve the repository root with any static HTTP server and open `index.html`. A local server is recommended for service-worker/PWA testing. Internet access is needed for external data services.

## License

MIT. Third-party services and map data remain subject to their own terms and attribution requirements.
