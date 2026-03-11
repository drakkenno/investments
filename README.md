# Gold Price Dashboard

A responsive, real-time gold price dashboard with historical price tracking and multiple time period views (day, week, month, year, lifetime).

## Features

- 💰 **Current Gold Price Display**: Shows the latest gold price with change metrics
- 📈 **Interactive Price Charts**: View historical price data with Chart.js
- ⏱️ **Multiple Time Periods**: Switch between 1 day, 1 week, 1 month, 1 year, and lifetime views
- 💱 **Multi-Currency Support**: View prices in USD, EUR, or GBP
- 📊 **Price Statistics**: High, low, average prices, and percentage change
- 📱 **Fully Responsive**: Works seamlessly on desktop, tablet, and mobile devices
- 🎨 **Modern Dark Theme**: Beautiful gradient-based UI with smooth animations
- ⚡ **Zero Dependencies** (except Chart.js): Runs entirely client-side

## Getting Started

### Option 1: Deploy to GitHub Pages

1. **Fork or Clone this Repository**
   ```bash
   git clone https://github.com/yourusername/investments.git
   cd investments
   ```

2. **Enable GitHub Pages**
   - Go to your repository settings
   - Scroll to "GitHub Pages" section
   - Select `main` branch as source
   - Save

3. **Access Your Dashboard**
   - Visit `https://yourusername.github.io/investments/`

### Option 2: Run Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/investments.git
   cd investments
   ```

2. **Open in browser**
   - Simply open `index.html` in your web browser

3. **Or use a simple HTTP server**
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   
   # Node.js with http-server
   npx http-server
   ```

## Current Implementation

The dashboard currently uses **mock data generation** for demonstration purposes. This allows it to work entirely client-side with no backend required, making it perfect for GitHub Pages.

The mock data generator creates realistic price fluctuations based on a base price of $2,050/oz.

## Upgrading to Real API Data

To use real gold price data, you can integrate with these free APIs:

### Option 1: Metals API (Free Tier)

```javascript
// Get API key from https://metals-api.com
const API_KEY = 'your_api_key_here';
const API_URL = `https://metals-api.com/api/latest?access_key=${API_KEY}&base=USD&symbols=XAU`;

async function fetchRealGoldPrices() {
    try {
        const response = await fetch(API_URL);
        const data = await response.json();
        // Process data...
    } catch (error) {
        console.error('Error fetching gold prices:', error);
    }
}
```

### Option 2: Finnhub API

Get free API key from https://finnhub.io and fetch commodity data.

### Option 3: Alpha Vantage

Free tier available at https://www.alphavantage.co

## File Structure

```
investments/
├── index.html           # Main dashboard (all-in-one file)
├── README.md           # This file
└── .git/               # Git repository data
```

## Customization

### Change Base Currency
Modify the `currencyRates` object in the script section to adjust conversion rates.

### Modify Colors
Update the gradient colors in the CSS:
- Gold accent: `#ffd700` (change throughout CSS)
- Background: `linear-gradient(135deg, #1e1e2e 0%, #2d2d44 100%)`

### Adjust Price Range
In the `generateMockData()` function, modify:
```javascript
currentPrice = Math.max(1800, Math.min(2500, currentPrice)); // Change min/max
```

### Change Auto-Refresh Interval
Modify the interval at the bottom:
```javascript
setInterval(function() {
    // ... refresh logic
}, 5 * 60 * 1000); // Currently 5 minutes, change to desired value
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## API Notes

- **Current Data**: Using mock data generator
- **Chart.js**: Loaded from CDN (cdn.jsdelivr.net)
- **No Backend Required**: Fully static site - perfect for GitHub Pages
- **CORS Friendly**: When using real APIs, ensure they support CORS or use a CORS proxy

## Future Enhancements

- [ ] Integration with real-time metal prices API
- [ ] Add more metals (silver, platinum, palladium)
- [ ] Export data as CSV
- [ ] Add price alerts
- [ ] Save user preferences in localStorage
- [ ] Add technical analysis indicators

## License

This project is open source and available under the MIT License.

## Support

For issues or suggestions, please create a GitHub issue in the repository.

---

**Note**: This is a demonstration dashboard with mock data. For production use with real gold prices, integrate with a reliable commodity API.
