#  API INTEGRATION

*COMPANY*: CODTECH IT SOLUTIONS

*NAME*: AMAN KUMAR

*INTERN ID*: CT04DM776

*DOMAIN*: Full Stack Web Development

*DURATION*: 4 WEEKS

*MENTOR*: NEELA SANTOSH

"I am Aman Kumar is a passionate developer with a keen interest in web technologies and API integrations. With guidance from mentor Neela Santosh,I am building a weather webpage that dynamically fetches and displays data from a public API, enhancing real-time user experience."

Now, here’s an HTML, CSS, and JavaScript-based webpage that integrates with a weather API to fetch and display live weather data:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weather Info</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        #weather {
            margin-top: 20px;
            padding: 20px;
            border: 1px solid #ddd;
            display: inline-block;
        }
    </style>
</head>
<body>
    <h1>Weather Information</h1>
    <input type="text" id="city" placeholder="Enter city name">
    <button onclick="getWeather()">Get Weather</button>
    <div id="weather"></div>

    <script>
        async function getWeather() {
            const city = document.getElementById('city').value;
            const apiKey = 'YOUR_API_KEY'; // Replace with your actual API key
            const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`;

            try {
                const response = await fetch(url);
                const data = await response.json();
                document.getElementById('weather').innerHTML = `
                    <h2>${data.name}</h2>
                    <p>Temperature: ${data.main.temp} °C</p>
                    <p>Weather: ${data.weather[0].description}</p>
                `;
            } catch (error) {
                document.getElementById('weather').innerHTML = `<p>Error fetching data</p>`;
            }
        }
    </script>
</body>
</html>

How it works:
The user enters a city name.

The JavaScript function getWeather() fetches weather data using OpenWeatherMap API.

The response is displayed dynamically on the webpage.

To make it work, you need an API key from OpenWeatherMap, which you’ll replace in the placeholder YOUR_API_KEY.

<div class="weather-icon">
      <img src="" alt="">
</div>
