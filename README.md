# Zimbabwe Stay & Explore

**Design and Development of a Web-Based Tourism Discovery and Location-Based Recommendation System for Zimbabwe**

Author: Honest Kudzai Dube

## Overview

Tourists in Zimbabwe often have to check several websites to find out what is near their hotel, how far it is, and how to get there. This project brings that information together in one place.

The central feature is **Explore Around My Stay**. A tourist picks a hotel, says how many days they are staying, and the system shows nearby attractions, activities, restaurants and cultural sites with distances, travel times and directions. They can then build a day-by-day itinerary.

**Phase one covers three destinations:** Victoria Falls, Nyanga and Masvingo.

## Aim

To design and develop a web-based tourism discovery and recommendation system that connects tourists with accommodation facilities and nearby tourist attractions in Zimbabwe.

## Objectives and where they are met

| # | Objective | How the system meets it |
|---|-----------|-------------------------|
| 1 | Centralised database of hotels, lodges and attractions | `SEED` object in `index.html` (6 hotels, 17 places) |
| 2 | Location-based recommendations around a hotel | `nearby()` filters by destination, interest and radius, sorted by distance |
| 3 | Distances, directions and travel times | Haversine formula, road estimate, drive and walk times, Google Maps directions link, Leaflet map |
| 4 | Personalised itineraries | Itinerary panel: add places, suggest a plan, move items between days, print |
| 5 | Activities, restaurants and cultural experiences | Place types: Attractions, Activities, Restaurants, Culture |
| 6 | Administrative interface | Admin tab: add or delete hotels and places, export JSON, log out |

## Features

- Choose a destination and hotel, then see nearby places closest first
- Filter by interest (attractions, activities, restaurants, culture) and search radius (5 to 150 km)
- Distance by road (estimated), driving time and walking time for each place
- Interactive map showing the hotel and nearby places
- One-click directions in Google Maps
- Itinerary builder with automatic suggestions and a print view
- PIN-protected admin area with log out
- Zimbabwe flag logo and favicon

## Technology

- HTML, CSS and JavaScript (no framework, no build step)
- [Leaflet](https://leafletjs.com/) for the map, with [OpenStreetMap](https://www.openstreetmap.org/) tiles
- Google Fonts (Bricolage Grotesque)
- Browser `localStorage` to keep admin changes during the demo

## How to run

1. Create a folder, for example `C:\Projects\zimbabwe-tourism`, and put `index.html` in it.
2. Open the folder in Visual Studio Code (**File > Open Folder**) and choose to trust it.
3. Install the **Live Server** extension.
4. Right-click `index.html` and choose **Open with Live Server**.

You can also open `index.html` directly in Chrome or Edge. An internet connection is needed for the map tiles, fonts and map library.

> If VS Code's built-in preview shows "File does not reside within a trusted folder", open the folder as in step 2, or use a normal browser.

## How to use

**Tourists**
1. Select a destination and a hotel.
2. Set the number of days and the search radius, and pick your interests.
3. Browse the results, tap **Get directions**, or **Add to itinerary**.
4. Use **Suggest a plan** to spread the nearest places across your days, then adjust each item's day.
5. Use **Print** to save or print the itinerary.

**Administrators**
1. Open the **Admin** tab and enter the PIN.
2. Add a hotel or a place with its name, destination, type, coordinates and details.
3. Delete records from the Records table.
4. **Download data (JSON)** saves a copy of all records. **Reset to sample data** restores the starting data.
5. Use **Log out** when finished.

## How the recommendations work

1. The straight-line distance between the hotel and each place is calculated with the Haversine formula.
2. Road distance is estimated as 1.3 times the straight-line distance.
3. Travel time assumes 45 km/h by car and 4.5 km/h on foot.
4. Places in the same destination, within the chosen radius and matching the chosen interests are listed from nearest to farthest.

## Project structure

```
zimbabwe-tourism/
├── index.html   # page, styles, data and logic in one file
└── README.md
```

## Limitations

- Coordinates, prices and opening hours are approximate sample data and should be verified before use.
- Road distances and travel times are estimates, not live routing.
- Data is stored in the browser, so each browser has its own copy.
- The admin PIN is stored in the page's JavaScript and is not real security.
- Only three destinations are covered.

## Credits

- Map library: Leaflet
- Map data: © OpenStreetMap contributors
- Font: Bricolage Grotesque (Google Fonts)
