# 🌊 Flood Response Portal

## Overview

The **Flood Response Portal** is a real-time, interactive web application designed to help users prepare for and respond to flood emergencies. It provides live weather data, flood risk assessment, shelter locations, safe routes, and community support coordination—all in a unified dashboard.

The application is built as a **single-page HTML application** with modern UI design, responsive layout, and dark/light theme support. It integrates with free public APIs for weather, location services, and flood forecasting.

---

## 🎯 Key Features

### 1. **Real-time Dashboard**
- Live weather data and rainfall monitoring
- Water level tracking and flood risk assessment
- Dynamic status indicators (Safe, Warning, Critical)
- Time-stamped data updates

### 2. **Interactive Flood Map**
- Leaflet.js-powered interactive mapping
- Flood risk visualization with color-coded zones
- Citizen report markers for waterlogging and urgent needs
- Click-to-report functionality for community input

### 3. **Flood Risk Analysis**
- Risk model derived from rainfall, water levels, and historical data
- Trend analysis with multi-axis charts
- Hourly forecast for 24-hour planning window

### 4. **Shelter Locator**
- Lists nearby emergency shelters by location
- Contact information and availability status
- Distance-based sorting

### 5. **Route & Roads Information**
- Blocked roads and alternate routes display
- Road status indicators (Open/Flooded/Caution)
- Traffic impact assessment

### 6. **Community Help Network**
- **Offers**: Residents can post available resources (food, water, shelter, medical supplies, charging points)
- **Urgent Requests**: Users can request help (rescue, food, water, medical assistance)
- Direct contact coordination between community members
- Real-time posting and display

### 7. **Emergency Alerts**
- Official advisories based on flood status
- Community notes and safety tips
- Location-based notifications

### 8. **Accessibility Features**
- Dark and light theme toggle
- Responsive design for mobile and desktop
- Geolocation support (use your current location)
- Search by city name

---

## 🛠️ Technology Stack

### Frontend
- **HTML5**: Semantic markup and structure
- **CSS3**: Custom properties (CSS variables) for theming, CSS Grid, Flexbox
- **Vanilla JavaScript**: No framework dependencies for lightweight performance

### External Libraries & APIs
- **Leaflet.js** (v1.9.4): Interactive mapping
- **Chart.js**: Data visualization for trend analysis
- **Bootstrap Icons**: Icon library for UI elements
- **Inter Font** (Google Fonts): Clean, modern typography

### Data APIs
- **Open-Meteo API**: Free weather forecast and flood forecasting data
- **Nominatim API**: Location search and geocoding
- **Flood API Integration**: Real-time water level and flood risk data

---

## 📁 Project Structure

```
flood-response-portal.html
├── <head>
│   ├── Meta tags (charset, viewport, title)
│   ├── Font imports (Inter, Bootstrap Icons)
│   ├── Library imports (Leaflet, Chart.js)
│   └── CSS (Embedded)
│
└── <body>
    ├── Sidebar Navigation
    │   ├── Brand/Logo
    │   ├── Navigation links
    │   └── Emergency contacts & info cards
    │
    ├── Main Dashboard
    │   ├── Topbar (search, theme toggle, location, refresh)
    │   ├── KPI Cards (4-column grid)
    │   ├── Flood Map & Summary
    │   ├── Shelters & Roads sections
    │   ├── Community Help
    │   ├── Alerts & Notices
    │   ├── Trend Analysis Chart
    │   └── Footer
    │
    └── JavaScript (Embedded)
        ├── State management
        ├── API integration functions
        ├── Data rendering functions
        ├── Event handlers
        └── Chart initialization
```

---

## 🎨 Design System

### Color Scheme (Light Theme)
- **Primary**: `#0b66ff` (Blue)
- **Danger**: `#dc2626` (Red)
- **Warning**: `#d97706` (Orange)
- **Success**: `#15803d` (Green)
- **Background**: `#f4f7fb` (Light Gray)
- **Surface**: `#ffffff` (White)

### Color Scheme (Dark Theme)
- **Primary**: `#5aa2ff` (Light Blue)
- **Danger**: `#f87171` (Light Red)
- **Warning**: `#f59e0b` (Light Orange)
- **Success**: `#4ade80` (Light Green)
- **Background**: `#09111f` (Dark Navy)
- **Surface**: `#0f172a` (Dark Slate)

### Layout
- **Sidebar**: Fixed 280px width (collapsible on mobile)
- **Main Content**: Responsive grid layout
- **KPI Grid**: 4 columns on desktop, 1 column on mobile
- **Border Radius**: 18px (primary), 14px (cards), 12px (buttons)
- **Box Shadow**: Subtle elevation (8px-14px offset)

---

## 🔌 API Integration

### Open-Meteo Weather API
```javascript
// Fetches real-time weather and forecast data
// Endpoints used:
// - forecast: Get hourly rainfall and temperature
// - flood: Get flood risk indicators
```

### Nominatim Geocoding API
```javascript
// Reverse geocoding for location search
// Input: City name
// Output: Latitude, longitude, formatted address
```

---

## 📊 Key Data Models

### Location Object
```javascript
{
  name: "Mumbai, Maharashtra, India",
  lat: 19.0760,
  lon: 72.8777
}
```

### Risk Model
```javascript
{
  status: "Warning|Critical|Safe",
  floodRisk: 0-100,
  waterLevel: 2.45,
  rainfall24h: 156.5,
  updatedAt: "2024-01-15T14:30:00Z",
  trendRain: [12, 15, 18, ...],
  trendTimes: ["2024-01-15T14:00Z", ...]
}
```

### Community Item
```javascript
{
  kind: "offer|request",
  type: "food|water|shelter|medical|charging", // for offers
  name: "John Doe",
  area: "Sector 5, Mumbai",
  contact: "+91-9999-9999", // offers only
  notes: "Need medical supplies", // requests only
  time: "5 minutes ago"
}
```

---

## 🚀 How to Use

### 1. **Search for a Location**
   - Enter a city name in the search bar
   - Click "Search" or press Enter
   - Dashboard updates with live data for that location

### 2. **Use Your Current Location**
   - Click "Use my location" button
   - Grant geolocation permission
   - Dashboard loads data for your current position

### 3. **Refresh Live Data**
   - Click "Refresh live data" button
   - System fetches latest weather, water levels, and flood status
   - KPIs and charts update automatically

### 4. **View Flood Map**
   - Scroll to "Flood map" section
   - See color-coded flood risk zones
   - Click to add citizen reports (waterlogging, urgent needs)

### 5. **Find Shelters**
   - Scroll to "Shelters" section
   - View nearby emergency shelters
   - Check status and contact details

### 6. **Check Safe Routes**
   - Scroll to "Roads & routes" section
   - See road status (Open/Flooded/Caution)
   - Plan alternate routes based on blocked roads

### 7. **Post Help Offers**
   - Go to "Community help" → "Post an offer"
   - Select type (food, water, shelter, medical, charging)
   - Fill in details (name, area, contact)
   - Submit to notify nearby residents

### 8. **Request Help**
   - Go to "Community help" → "Post a request"
   - Select type of help needed
   - Describe your location and requirements
   - Submit for community response

### 9. **Toggle Theme**
   - Click "Theme" button in topbar
   - Switch between light and dark mode
   - Theme persists during session

### 10. **View Trend Analysis**
   - Scroll to bottom for rainfall and water level trends
   - See 24-hour forecast with dual-axis chart
   - Use for planning and decision-making

---

## 📱 Responsive Design

The application is fully responsive:
- **Desktop (1080px+)**: Sidebar + main content side-by-side
- **Tablet (768px-1080px)**: Responsive grid adjustments
- **Mobile (<768px)**: Single column layout, collapsible navigation

### Breakpoint Media Query
```css
@media (max-width: 1080px) {
  .app { grid-template-columns: 1fr; }
  .sidebar { position: relative; height: auto; }
  /* All grids revert to single column */
}
```

---

## 🔒 Data Integrity & Safety

### Input Sanitization
- HTML escaping for user-generated content (community posts)
- Email/phone validation for contact forms
- Character encoding for international characters

### Security Notes
- No sensitive data stored locally; uses public APIs only
- API calls are read-only for weather/location data
- Community data stored in client-side state only (no backend)
- HTTPS-ready (all external resources support HTTPS)

---

## ⚙️ JavaScript Functions Reference

### Core Functions

#### `fetchLiveFloodData(lat, lon)`
Fetches weather, rainfall, water level, and flood data from Open-Meteo API.

#### `geocodePlace(query)`
Converts city name to coordinates using Nominatim API.

#### `deriveRiskModel(payload)`
Calculates flood risk status and trends from raw API data.

#### `renderMap(location, model)`
Initializes Leaflet map with flood risk visualization.

#### `renderKPIs(location, model)`
Updates key performance indicators (rainfall, water level, risk score).

#### `renderChart(model)`
Creates dual-axis trend chart using Chart.js (rainfall vs. water level).

#### `updateDashboard(customLocation)`
Main orchestration function that updates all dashboard sections.

#### `escapeHtml(text)`
Sanitizes user input to prevent XSS attacks.

---

## 🚨 Emergency Contacts (India)

Built into the application:
- **NDRF Helpline**: 1078
- **Emergency**: 112
- **Ambulance**: 108

---

## 📝 Example Workflow

1. User opens the portal
2. Portal loads default location (Mumbai) with live flood data
3. KPIs show current rainfall: 45mm, water level: 1.8m, risk: 35%
4. User sees "Warning" status with yellow alert pill
5. User checks map and sees flood zones in orange
6. User scrolls to shelters and finds 3 nearby options
7. User posts community offer: "Have extra water bottles in Sector 5"
8. Another user sees the offer and calls the contact number
9. User clicks "Refresh live data" → status upgrades to "Critical"
10. Official advisory updates: "Move to safer ground"
11. User switches to dark theme for better readability
12. User checks roads and sees alternate routes available

---

## 🐛 Known Limitations

1. **Community data persistence**: Not saved between sessions (client-side only)
2. **Map markers**: Limited to 50 citizen reports (performance)
3. **API rate limits**: Open-Meteo free tier has ~10 requests/minute
4. **Geolocation**: Requires HTTPS on production
5. **Offline support**: None (requires live internet connection)
6. **Data accuracy**: Relies on 3rd-party API accuracy; not guaranteed for critical decisions

---

## 🔮 Future Enhancements

- [ ] Backend database for persistent community data
- [ ] User authentication for offer/request tracking
- [ ] Push notifications for critical alerts
- [ ] Offline mode with cached data
- [ ] Integration with official weather bureaus
- [ ] SMS/WhatsApp notification support
- [ ] Multi-language support
- [ ] Historical data trends
- [ ] Predictive flood models (machine learning)
- [ ] Integration with disaster management agencies

---

## 📄 License

This project is open-source and available for public use, improvement, and community contribution.

---

## 🤝 Contributing

To contribute to this project:
1. Report bugs or suggest features via issues
2. Submit improvements with detailed descriptions
3. Follow the existing code style and conventions
4. Test thoroughly before submitting changes

---

## 📞 Support & Contact

For questions, bug reports, or suggestions:
- Review emergency contacts in the sidebar
- Check the "What users need during floods" information card
- Use community help features for local assistance

---

## 🙏 Acknowledgments

- **Open-Meteo**: Free weather and flood forecast API
- **Nominatim/OSM**: Location data and geocoding
- **Leaflet.js**: Open-source mapping library
- **Chart.js**: Data visualization library
- **Bootstrap Icons**: Clean icon set

---

## ⚠️ Disclaimer

This portal is designed to provide **informational support during flood emergencies**. Always follow official government advisories and local disaster management authorities. This application complements but does not replace official warnings and emergency services.

For life-threatening emergencies, **always call 112 (emergency) or local authorities first**.

---

**Last Updated**: January 2025
**Version**: 1.0
**Status**: Production Ready
