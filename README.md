# JavaScript Weather Dashboard

A responsive weather dashboard built with vanilla JavaScript and the Open-Meteo API. The project focuses on modern asynchronous JavaScript, modular architecture, resilient API handling, accessibility, and responsive UI design.

## Features

- Search weather for cities worldwide
- Current temperature, humidity, wind speed, and local time
- Five-day weather forecast
- Open-Meteo weather and geocoding APIs
- `async/await` based request flow
- Parallel requests with `Promise.all`
- Automatic retry with exponential backoff
- `AbortController` to cancel stale searches
- Custom Promise queue with a concurrency limit of two
- ES Modules for clean separation of responsibilities
- Responsive desktop and mobile interface
- Accessible status updates with `aria-live`

## Technologies

- HTML5
- CSS3
- JavaScript ES6+
- ES Modules
- Fetch API
- REST APIs
- Open-Meteo API

## Project Structure

```text
JavaScript-Weather-Dashboard/
├── index.html
├── styles.css
├── README.md
└── js/
    ├── app.js
    ├── api.js
    ├── config.js
    ├── queue.js
    └── ui.js
```

## Architecture

- `app.js` coordinates searches, request cancellation, and parallel loading
- `api.js` handles API requests, retries, geocoding, and URL construction
- `config.js` stores endpoints and retry settings
- `queue.js` implements the custom concurrency queue
- `ui.js` renders weather data, forecasts, loading states, and errors

## Reliability Features

The dashboard is designed to behave well even when network conditions are unreliable:

1. Failed requests are retried up to three times using exponential backoff.
2. A new search cancels the previous unfinished search with `AbortController`.
3. Current weather and forecast data load in parallel with `Promise.all`.
4. A custom Promise queue limits concurrent API work.

## Run Locally

Because the project uses ES Modules, run it through a local web server instead of opening `index.html` directly.

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Deployment

This is a static frontend project and can be deployed directly using Vercel, Netlify, or GitHub Pages.

For Vercel:

1. Push this repository to GitHub.
2. Import the repository into Vercel.
3. Choose `Other` as the framework preset if asked.
4. Leave the build command and output directory empty.
5. Deploy.

## Data Source

Weather and geocoding data are provided by Open-Meteo.

## What I Practiced

This project helped me practice asynchronous JavaScript, API integration, modular code organization, request cancellation, retry strategies, controlled concurrency, responsive design, and accessible UI states.
