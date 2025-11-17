# Weather App

A simple client-side Weather App that uses the OpenWeatherMap API to display current weather (temperature, humidity, wind speed, and an icon) for a searched city.

## Project structure

- `index.html` — The main HTML file with the UI and JavaScript.
- `styles.css` — Styling for the card UI.
- `images/` — Icons used by the app (search, weather icons, humidity, wind, etc.).

## Features

- Search for a city name and fetch current weather (metric units).
- Displays temperature, humidity, wind speed and a weather icon.
- Simple, mobile-friendly card UI.

## Setup

1. Get an OpenWeatherMap API key:

   - Create an account at https://openweathermap.org/ and get an API key (Application ID).

2. Add your API key in `index.html`:

   Open `index.html` and locate the line:

   ```js
   const apiKey = "3b17b20738c3775cf9d66f460964e247";
   ```

   Replace the string with your own key. Example:

   ```js
   const apiKey = "YOUR_API_KEY_HERE";
   ```

3. Make sure the `images/` folder is present and contains the images referenced by `index.html` (search.png, rain.png, clouds.png, clear.png, drizzle.png, mist.png, humidity.png, wind.png).

4. Open the app in a browser:

   - The simplest approach is to open `index.html` directly in your browser (double-click the file or right-click → Open with > your browser).
   - For a nicer local dev workflow, use the VS Code Live Server extension, or run a lightweight HTTP server.

   Example using `npx` (if you have Node.js):

   ```cmd
   npx http-server . -p 8080
   ```

   Then visit `http://localhost:8080` in your browser.

## Git (example)

To stage and commit the initial files from the project root (Windows `cmd.exe`):

```cmd
git add .
git commit -m "first commit"
```

If `git commit` previously reported "nothing added to commit but untracked files present", that means you must first `git add` the files (see commands above).

## Known issues & quick fixes

While using the provided `index.html`, you may encounter a few small bugs or behavior issues. Here are some recommended quick fixes you can apply if needed:

- Fix wind markup: there is a typo in the provided HTML around the wind value:

  ```html
  <p class="wind">15 km/hr/p></p>
  ```

  It should be:

  ```html
  <p class="wind">15 km/hr</p>
  ```

- Weather condition checks are case-sensitive. The API typically returns capitalized weather main values such as `Clear`, `Clouds`, `Rain`, etc. Make your checks either match the exact case or normalize with `toLowerCase()`.

- Image assignment typos in the JS: use `weatherIcon.src = "images/clear.png";` (property `src`, not `scr`).

- When showing the `.weather` container, avoid leading whitespace in `style.display` values (use `"block"` not `" block"`).

If you'd like, I can apply these small fixes directly to `index.html` and add a quick unit or manual test page to confirm behavior.

