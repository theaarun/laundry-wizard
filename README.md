# 🧺 Laundry Wizard: Intelligent Laundry Forecast

**Laundry Wizard** is a web-based utility that takes the guesswork out of hanging laundry. Instead of just checking if it’s "sunny," this app uses real-time meteorological data and a physics-based evaporation formula to calculate exactly how many minutes it will take for your clothes to dry based on their fabric type.

## ✨ Features

- **Real-time Weather Integration:** Connects to the **Open-Meteo API** to fetch live temperature, humidity, wind speed, and weather conditions for any city.
- **Physics-Based Estimation:** Uses a specialized evaporation formula rather than simple timers.
- **Fabric-Specific Calculations:** Adjusts drying times based on the density and surface area of the garment (e.g., Jeans vs. Bedsheets).
- **Safety Alerts:** Automatically warns users if high winds (hurricanes) or precipitation (rain/snow) make outdoor drying impossible.
- **Perfect Condition Detection:** Highlights when the "Golden Quadrant" of drying (high temp, low humidity, ideal breeze) is met.

## 🧪 The Science

The application calculates the drying time `T` (in minutes) using the following evaporation model:

$$T = \frac{K}{Temp \times (1 - RH) \times (1 + 0.1 \times W)}$$

### Variables
- **K (Fabric Constant):** Represents the moisture retention of specific materials.
- **Temp:** Current air temperature in Celsius.
- **RH:** Relative Humidity expressed as a decimal (e.g., 0.60 for 60%).
- **W:** Wind speed in km/

### Fabric Constants (K)

| Garment Type | Constant (K) | Why? |
| :--- | :--- | :--- |
| **Bedsheets** | 1200 | Large surface area but very thin; dries quickly. |
| **T-Shirts** | 1800 | Standard cotton knit; moderate thickness. |
| **Jeans / Denim** | 4500 | High density and thickness; holds significantly more water. |
| **Towels** | 5500 | Terry cloth loops trap moisture, requiring more energy to extract. |

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/theaarun/laundry-wizard](https://github.com/theaarun/laundry-wizard.git)

2. Open the App:
Simply open index.html in your browser. No server-side setup or Node.js is required; the app runs entirely on client-side JavaScript.

3. Usage:
- Type your city name into the search bar.
- Click Search to fetch local weather data.
- Click on a clothing item (e.g., "T-Shirt") to calculate the estimated drying time.

## ⚠️ "Perfect Drying" Criteria
The app will trigger a special "Perfect Conditions" badge if the weather meets the following ideal criteria:

- Sky: Clear or mainly clear (Weather Code 0-1)
- Humidity: < 70%
- Temperature: ≥ 21°C
- Wind: 12.8 km/h – 19.3 km/h (approx. 8–12 mph)

## 🛠️ Built With
HTML5 / CSS3
JavaScript (ES6)
Open-Meteo API (No API key required)

## 📝 License
This project is open-source and available under the MIT License.