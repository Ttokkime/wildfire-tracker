# Wildfire Tracker

A React-based single-page application that monitors global wildfire activity in real time using NASA's EONET REST API and Google Maps.

![Wildfire Tracker](https://img.shields.io/badge/React-18-blue) ![NASA API](https://img.shields.io/badge/NASA-EONET%20API-green) ![Google Maps](https://img.shields.io/badge/Google-Maps%20API-red)

## Features

- Real-time wildfire data from NASA's Earth Observatory Natural Event Tracker (EONET)
- Interactive Google Maps interface with fire markers at event coordinates
- Click any marker to see event ID and title
- Loading state while fetching data
- Graceful error handling if the API is unavailable

## Tech Stack

- **React 18** — component-based UI with hooks
- **@react-google-maps/api** — Google Maps integration
- **NASA EONET API v3** — live wildfire event data
- **@iconify/react** — fire icons

## Getting Started

### Prerequisites

- Node.js installed
- A Google Maps API key ([get one here](https://console.cloud.google.com/))

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Ttokkime/Wildfire-Tracker.git
   cd Wildfire-Tracker
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory:
   ```
   REACT_APP_GOOGLE_MAPS_API_KEY=your_api_key_here
   ```

4. Start the development server:
   ```bash
   npm start
   ```

The app will open at `http://localhost:3000`.

## Project Structure

```
src/
├── components/
│   ├── Map.js              # Google Maps + marker rendering
│   ├── LocationMarker.js   # Fire icon marker component
│   ├── LocationInfoBox.js  # Event info popup
│   ├── Header.js           # App header
│   └── Loader.js           # Loading spinner
├── App.js                  # Data fetching + app layout
└── index.css               # Global styles
```

## API

This project uses the [NASA EONET API v3](https://eonet.gsfc.nasa.gov/docs/v3):

```
GET https://eonet.gsfc.nasa.gov/api/v3/events?category=wildfires&status=open
```

## Notes

- The NASA EONET API occasionally experiences downtime. If no markers appear, check the API status directly at the URL above.
- Google Maps requires a valid API key with billing enabled. The free tier ($200/month credit) is sufficient for development use.
