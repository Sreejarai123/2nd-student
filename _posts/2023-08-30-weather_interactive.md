---
title: Weather App
layout: base
description: This is an interactive weather app that will help to inform you about the weather
categories: [C4.9]
type: hacks
courses: { compsci: {week: 2}}
---
<html>
<head>
  <title>Weather Map</title>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" />
  <style>
    #map {
      height: 300px;
    }
  </style>
</head>
<body>
  <h1>Weather Map</h1>
  <div id="map"></div>

  <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"></script>
  <script>
    const map = L.map('map').setView([0, 0], 2);
    
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '© OpenStreetMap contributors'
    }).addTo(map);
    
    const apiKey = 'YOUR_OPENWEATHERMAP_API_KEY';
    const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=cityname&appid=${apiKey}`;
    
    async function getWeather(cityName) {
      const response = await fetch(apiUrl.replace('cityname', cityName));
      const data = await response.json();
      return data;
    }
    
    function addMarkerToMap(lat, lon, weather) {
      const marker = L.marker([lat, lon]).addTo(map);
      marker.bindPopup(`Weather: ${weather}`).openPopup();
    }
    
    async function showWeatherOnMap(cityName) {
      const weatherData = await getWeather(cityName);
      const { lat, lon } = weatherData.coord;
      const weather = weatherData.weather[0].main;
      
      addMarkerToMap(lat, lon, weather);
    }
    
    // Example usage
    showWeatherOnMap('New York');
  </script>
</body>
</html>


