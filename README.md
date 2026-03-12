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

### Option 1: Deploy to GitHub Pages (Instant - No Setup!)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Add gold price dashboard"
   git push origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository settings
   - Scroll to "GitHub Pages" section
   - Select `main` branch as source
   - Save

3. **Access Your Dashboard**
   - Visit `https://yourusername.github.io/investments/`
   - It will immediately start fetching real gold prices!

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

## Real-Time Data Integration

The dashboard is integrated with **api.gold-api.com** for real, live gold prices - **completely free, no API key required!**

### How It Works

1. **Current Price**: Fetched in real-time from `https://api.gold-api.com/price/XAU`
2. **Price History**: Built from real snapshots saved in your browser's localStorage, accumulating over time
3. **Fallback**: If the API is unavailable, the dashboard uses the last saved real price from local history
4. **Auto-Refresh**: Prices update every 5 minutes automatically

### gold-api.com API

- **Website**: [api.gold-api.com](https://api.gold-api.com)
- **Cost**: Completely Free
- **No API Key**: Required! Just works out of the box
- **Rate Limits**: Generous free tier - perfect for client-side use
- **What You Get**: Real-time gold prices in USD and other assets via symbols

### Local Storage

The dashboard stores price history in your browser's localStorage:
- Automatically saves new price data as it's fetched
- Keeps up to 2 years of historical data
- Survives page refreshes and browser sessions
- No server required - works entirely client-side

## File Structure

```
investments/
├── index.html           # Main dashboard (all-in-one file)
├── README.md           # This file
└── .git/               # Git repository data
```

## Customization

### Change Colors
Update the gradient colors in the CSS:
- Gold accent: `#ffd700` (change throughout CSS)
- Background: `linear-gradient(135deg, #1e1e2e 0%, #2d2d44 100%)`

### Modify Currency Conversion Rates

Modify the `currencyRates` object in the script section:
```javascript
const currencyRates = {
    'USD': 1.0,
    'EUR': 0.92,    // Change these rates to match current values
    'GBP': 0.79
};
```

### Adjust Data Storage Limit

In the `savePriceHistory()` function, change how much history to keep:
```javascript
// Keep only last 2 years of data (modify this)
const twoYearsAgo = new Date();
twoYearsAgo.setFullYear(twoYearsAgo.getFullYear() - 2);
```

### Change Auto-Refresh Interval
Near the bottom of the script:
```javascript
}, 5 * 60 * 1000); // 5 minutes - change to desired value
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## API Notes

- **Current Data**: Using `GET https://api.gold-api.com/price/XAU`
- **Chart.js**: Loaded from CDN (cdn.jsdelivr.net)
- **No Backend Required**: Fully static site - perfect for GitHub Pages
- **CORS Friendly**: When using real APIs, ensure they support CORS or use a CORS proxy

## Future Enhancements

- [ ] Add more metals (silver, platinum, palladium)
- [ ] Export data as CSV
- [ ] Add price alerts (notify when price reaches certain levels)
- [ ] Save user preferences in localStorage (selected currency, time period)
- [ ] Add technical analysis indicators (MA, RSI, MACD)
- [ ] Dark/light theme toggle
- [ ] Add funding/costs calculations for gold investments

## License

This project is open source and available under the MIT License.

## Support

For issues or suggestions, please create a GitHub issue in the repository.

---

**✨ No Setup Required!** This dashboard works immediately out of the box. Real gold prices are fetched from [api.gold-api.com](https://api.gold-api.com) - completely free, no API key needed. Just push to GitHub Pages and you're live!
