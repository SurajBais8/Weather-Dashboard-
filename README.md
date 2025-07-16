# 🌦️ Weather Dashboard (Power BI)

This project is a **real-time Weather Dashboard** built using **Power BI**, powered by a Weather API (like OpenWeatherMap).  
It visually presents temperature, humidity, wind speed, and AQI with intuitive, color-coded insights.

---

## 📊 Key Features

- ✅ Real-time weather updates via Weather API
- 🌡️ Displays temperature, humidity, pressure, and wind speed
- 💨 Visual AQI status using dynamic **DAX-based color logic**
- 📅 City and date filters for easy drill-down
- 📊 Clean, interactive Power BI visuals

---

## 🔧 Tools Used

- **Power BI Desktop (.pbix)**
- **Weather API** (manual/automated data load)
- **DAX formulas** for KPI coloring and logic
- **Excel or CSV** as intermediate data storage (optional)

---

---

## 🧠 DAX Highlight (AQI Color Logic)

```dax
AQI Color = 
VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.pm10]), 0)
RETURN
    SWITCH(
        TRUE(),
        AQI <= 50, "#43d946",     // Good (Green)
        AQI <= 100, "#fff570",    // Moderate (Yellow)
        AQI <= 150, "#ff9800",    // Poor (Orange)
        AQI <= 200, "#d99343",    // Unhealthy (Red)
        AQI <= 300, "#ff5b0f",    // Severe (Purple)
        "#d95243"                 // Hazardous (Dark Maroon)
    )


