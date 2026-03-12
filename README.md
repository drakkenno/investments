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

## Real-Time & Historical Data Integration

The dashboard combines **two premium APIs** for comprehensive gold price data:

### Current Price: api.gold-api.com ✓ Free
- Real-time spot prices (gold offered in USD per troy ounce)
- 1-minute cache to prevent IP blocking
- No API key required

### Historical Prices: metalpriceapi.com 📊 Professional
- 30+ days to 2+ years of historical data
- Daily/hourly granularity available
- REST API: `https://api.metalpriceapi.com/v1/timeframe`
- API Key: `39e6e8602948c2a1d94378f894a0c755`
- 24-hour local cache to minimize API calls

### How It Works

1. **Current Price**: Fetched in real-time from gold-api.com when you load the page
2. **Price History**: Automatically fetched from metalpriceapi.com for your selected time period
3. **Local Caching**: 
   - Current price: cached 1 minute
   - Historical data: cached 24 hours
   - Fallback: uses browser localStorage if APIs are unavailable
4. **Auto-Refresh**: Prices update every 5 minutes
4. **Auto-Refresh**: Prices update every 5 minutes automatically

### gold-api.com (Real-Time)

- **Website**: [api.gold-api.com](https://api.gold-api.com)
- **Cost**: Completely Free
- **No API Key**: Required!
- **Endpoint**: `GET https://api.gold-api.com/price/XAU`
- **Rate Limits**: Generous free tier - perfect for client-side use (recommended 1-min cache)

### metalpriceapi.com (Historical)

- **Website**: [metalpriceapi.com](https://metalpriceapi.com)
- **Cost**: Paid plan (you have API key)
- **API Key**: Included in dashboard code
- **Endpoint**: `GET https://api.metalpriceapi.com/v1/timeframe`
- **What You Get**: Real-time + 30+ days to 2 years of historical precious metals prices
- **Response Format**: 
  ```json
  {
    "rates": {
      "2026-03-12": { "USDXAU": 5182.20 },
      "2026-03-13": { "USDXAU": 5190.45 }
    }
  }
  ```
  (USDXAU = USD price per troy ounce of gold)

### Local Storage

The dashboard stores data in your browser's localStorage:
- **Current price**: Cached for 1 minute (respects API fair-use policy)
- **Historical data**: Cached for 24 hours (reduces API quota usage)
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

### Modify API Configuration

The APIs are configured in the HTML file's script section:

```javascript
const API_BASE_URL = 'https://api.gold-api.com';                               // Current price API
const METALPRICEAPI_URL = 'https://api.metalpriceapi.com/v1';                  // Historical API
const METALPRICEAPI_KEY = '39e6e8602948c2a1d94378f894a0c755';                 // Your API key
const CACHE_TTL_MS = 60 * 1000;                                                // 1 minute - current price cache
const HISTORY_CACHE_TTL_MS = 24 * 60 * 60 * 1000;                              // 24 hours - historical cache
```

**To use your own metalpriceapi.com key**:
1. Sign up at [metalpriceapi.com](https://metalpriceapi.com/register)
2. Get your API key from the dashboard
3. Replace the `METALPRICEAPI_KEY` value in `index.html`
4. Adjust `HISTORY_CACHE_TTL_MS` based on your API quota (lower = more API calls)

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

**✨ Premium Setup!** This dashboard combines two APIs: free real-time prices from [api.gold-api.com](https://api.gold-api.com) + professional historical data from [metalpriceapi.com](https://metalpriceapi.com). Just push to GitHub Pages and you're live with real, accurate gold prices!
