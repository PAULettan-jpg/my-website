Core Objective & Functionality
Goal: To predict the likelihood of adverse weather conditions (e.g., "very hot," "very cold," "very wet," or "very uncomfortable") for long-term planning, directly answering the challenge prompt.

Output: A single, actionable Comfort Status (Hot, Cold, or Comfortable) for any given location and date.

Timeframe Analysis: Allows users to choose between Daily Data, Monthly Average, or Climatology (long-term historical average) for robust advance planning.

Technology and Data Sources
Primary Data Source: NASA POWER API is used for retrieving multi-decadal historical climate data.

Key Parameters: The app fetches and analyzes four essential meteorological variables:

T2M (Temperature at 2m, in  
∘
 C)

RH2M (Relative Humidity at 2m, in %)

WS2M (Wind Speed at 2m, in m/s)

PRECTOT (Total Precipitation, in mm)

Geospatial Tools: Leaflet.js provides the interactive map, while OpenStreetMap Nominatim handles the necessary geocoding (name ↔ coordinates) for location input and map clicks.

Comfort Analysis Logic (Heuristics)
The thermal comfort status is determined by the combined effect of the fetched parameters:

Hot Discomfort: Triggered if T2M >30 
∘
 C OR if the combination of T2M >25 
∘
 C and RH2M >70% indicates high heat stress.

Cold Discomfort: Triggered if T2M <10 
∘
 C OR if the combined effect of T2M <15 
∘
 C and WS2M >15 m/s indicates high wind chill.

Wet Condition Check: PRECTOT is reported and used to determine a 'Rainy' weather condition, directly addressing the "Very Wet" concern.

Comfortable Status: Assigned when none of the defined adverse thresholds are met.
