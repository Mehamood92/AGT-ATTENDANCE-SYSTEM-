# Office Hours Tracker — PWA

## Included
- `index.html`: the attendance application
- `manifest.webmanifest`: install metadata
- `sw.js`: app-shell caching for offline launches after first successful load
- `icons/`: install icons
- CSV import in Settings supports CSVs exported by this app, including date/entry/exit/break/status columns. Date conflicts prompt you to replace matching dates or keep existing records.

## Important hosting requirement
Progressive Web Apps need a secure context: host these files on HTTPS (or use localhost for development). Opening `index.html` directly from a file manager will run the page in a browser, but installability and service-worker offline support will not work.

## Deploy
1. Extract the ZIP.
2. Upload the *contents* of this folder to an HTTPS static host, preserving the `icons/` folder and file names.
3. Open the HTTPS URL in Chrome on Android and load it once online.
4. Use the browser menu → **Install app** or **Add to Home screen**. Some browsers show an in-app Install app button when the install prompt is available.
5. After installation, open it once online so the service worker can cache the app shell.

## Data and privacy
Attendance records remain in this browser's local storage. They are not synchronized to a server. Use Settings → Download backup / Export CSV regularly. Clearing browser storage can erase attendance data. An app install does not automatically transfer data between browsers or devices.

## Validation
The existing page includes `window.officeHoursTrackerTests()` for basic calculation test cases. Run the app from an HTTPS host, open browser developer tools, and call that function in the console. These are lightweight arithmetic checks, not a full end-to-end test suite.
