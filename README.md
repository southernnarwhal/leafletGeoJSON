# Leaflet Map Project

## Project Description
This project demonstrates how to create a simple interactive map using Leaflet.js. The map is centered on Svalbard Island and includes various features such as markers, a custom basemap, and different shapes (line, triangle, hexagon, and circle).

## Features
1. **Custom Basemap**: The map uses the Esri World Imagery basemap.
2. **Marker**: A marker is placed at the center of Svalbard Island with a popup message.
3. **Line**: A red line is drawn on the map.
4. **Triangle**: A blue triangle is drawn on the map.
5. **Hexagon**: A green hexagon is drawn on the map.
6. **Circle**: A yellow circle with a red fill is drawn on the map.

## Code Overview
### HTML Structure
The `index.html` file includes the necessary Leaflet.js CSS and JavaScript files and sets up a `div` element with the id `map` to hold the map.

### JavaScript
The JavaScript code initializes the map, sets the view to Svalbard Island, and adds the Esri World Imagery basemap. It also adds the following features to the map:
- A marker with a popup message.
- A red line.
- A blue triangle.
- A green hexagon.
- A yellow circle with a red fill.

### Example Code
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Leaflet Map</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
    <style>
        #map {
            height: 100vh;
        }
    </style>
</head>
<body>
    <div id="map"></div>
    <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
    <script>
        var map = L.map('map').setView([78.2232, 15.6469], 13);

        var Esri_WorldImagery = L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
            attribution: 'Tiles &copy; Esri &mdash; Source: Esri, i-cubed, USDA, USGS, AEX, GeoEye, Getmapping, Aerogrid, IGN, IGP, UPR-EGP, and the GIS User Community'
        });

        Esri_WorldImagery.addTo(map);

        // Adding a marker
        var marker = L.marker([78.2232, 15.6469]).addTo(map);
        marker.bindPopup("<b>Welcome to Svalbard!</b><br>This is Svalbard Island.").openPopup();

        // Adding a line
        var line = L.polyline([
            [78.2232, 15.6469],
            [78.2242, 15.6469]
        ], {color: 'red'}).addTo(map);

        // Adding a triangle
        var triangle = L.polygon([
            [78.2232, 15.6469],
            [78.2242, 15.6469],
            [78.2237, 15.6480]
        ], {color: 'blue'}).addTo(map);

        // Adding a hexagon
        var hexagon = L.polygon([
            [78.2232, 15.6469],
            [78.2237, 15.6464],
            [78.2242, 15.6469],
            [78.2242, 15.6474],
            [78.2237, 15.6479],
            [78.2232, 15.6474]
        ], {color: 'green'}).addTo(map);

        // Adding a circle
        var circle = L.circle([78.2232, 15.6469], {
            color: 'yellow',
            fillColor: '#f03',
            fillOpacity: 0.5,
            radius: 50
        }).addTo(map);
    </script>
</body>
</html>