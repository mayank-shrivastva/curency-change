<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Service Cost Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        label {
            display: block;
            margin: 10px 0 5px;
        }
        input {
            margin-bottom: 15px;
            width: 200px;
            padding: 5px;
        }
    </style>
</head>
<body>
    <h1>Service Cost Calculator</h1>
    <form id="costForm">
        <label for="numServices">Select Number of Services:</label>
        <input type="number" id="numServices" min="1" required>

        <label for="numPhotos">Total Number of Photos:</label>
        <input type="number" id="numPhotos" min="1" required>

        <label for="primaryCost">Primary Cost (in your currency):</label>
        <input type="text" id="primaryCost" readonly>

        <label for="downPayment">Down Payment (10% of Actual Cost):</label>
        <input type="text" id="downPayment" readonly>

        <label for="actualCost">Actual Cost (in your currency):</label>
        <input type="text" id="actualCost" readonly>

        <button type="submit">Calculate Costs</button>
    </form>

    <script>
        let usdToLocalRate = 1; // To store the exchange rate
        let localCurrencySymbol = ""; // To store the local currency symbol

        // Function to get user's current location
        function getUserLocation() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(showPosition, showError);
            } else {
                alert("Geolocation is not supported by this browser.");
            }
        }

        // Function to handle the user's location and fetch country/currency
        function showPosition(position) {
            const geolocationAPI = `https://ipapi.co/json/`;

            fetch(geolocationAPI)
                .then(response => response.json())
                .then(data => {
                    const country = data.country_name;
                    const currency = getCurrencyByCountry(data.country_code);
                    localCurrencySymbol = data.currency; // Get local currency symbol
                    fetchExchangeRates(currency);
                })
                .catch(error => console.error("Error fetching location:", error));
        }

        // Map country codes to currency codes
        function getCurrencyByCountry(countryCode) {
            const countryCurrencyMap = {
                "US": "USD",
                "IN": "INR",
                "GB": "GBP",
                "CA": "CAD",
                "JP": "JPY",
                "EU": "EUR",
                // Add more country-to-currency mappings as needed
            };
            return countryCurrencyMap[countryCode] || "USD"; // Default to USD if not mapped
        }

        // Fetch exchange rates and convert USD to local currency
        function fetchExchangeRates(currency) {
            const apiURL = "https://open.er-api.com/v6/latest/USD";

            fetch(apiURL)
                .then(response => response.json())
                .then(data => {
                    if (data.result === "success") {
                        const rates = data.rates;
                        usdToLocalRate = rates[currency];
                    } else {
                        console.error("Failed to retrieve exchange rates.");
                    }
                })
                .catch(error => console.error("Error fetching exchange rates:", error));
        }

        // Handle errors in geolocation
        function showError(error) {
            switch (error.code) {
                case error.PERMISSION_DENIED:
                    alert("User denied the request for Geolocation.");
                    break;
                case error.POSITION_UNAVAILABLE:
                    alert("Location information is unavailable.");
                    break;
                case error.TIMEOUT:
                    alert("The request to get user location timed out.");
                    break;
                case error.UNKNOWN_ERROR:
                    alert("An unknown error occurred.");
                    break;
            }
        }

        // Calculate costs on form submission
        document.getElementById("costForm").addEventListener("submit", function(event) {
            event.preventDefault();

            const numServices = parseInt(document.getElementById("numServices").value);
            const numPhotos = parseInt(document.getElementById("numPhotos").value);
            const serviceCostINR = 4; // Cost per service in INR

            // Calculate primary cost in INR
            const primaryCostINR = numServices * serviceCostINR * numPhotos;

            // Convert primary cost to local currency
            const primaryCostLocal = primaryCostINR * usdToLocalRate;
            document.getElementById("primaryCost").value = `${localCurrencySymbol}${primaryCostLocal.toFixed(2)}`;

            // Calculate down payment (10%)
            const downPayment = primaryCostLocal * 0.10;
            document.getElementById("downPayment").value = `${localCurrencySymbol}${downPayment.toFixed(2)}`;

            // Set actual cost to primary cost in local currency
            document.getElementById("actualCost").value = `${localCurrencySymbol}${primaryCostLocal.toFixed(2)}`;
        });

        // Call the function to get user's location on page load
        window.onload = function() {
            getUserLocation();
        };
    </script>
</body>
</html>
