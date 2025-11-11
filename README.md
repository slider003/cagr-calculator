# Compound Growth Calculator

<div align="center">

**A beautiful, interactive compound growth visualization tool**

[View Demo](#) | [Report Bug](#) | [Request Feature](#)

</div>

---

## Overview

A powerful yet elegant web application for visualizing compound annual growth rate (CAGR) calculations. Built with vanilla JavaScript and Chart.js, this calculator provides real-time visualization of investment growth with support for recurring contributions, scenario comparisons, and multiple export formats.

## Features

### Core Functionality
- **Real-time Calculations** - Instant updates as you adjust parameters
- **Interactive Sliders** - Smooth, responsive controls for all inputs
- **Animated Charts** - Beautiful Chart.js visualizations with milestone annotations
- **Recurring Contributions** - Support for monthly, quarterly, and annual contributions
- **Compound Interest Formula** - Accurate calculations using `FV = PV × (1 + r)^t`

### Advanced Features
- **Scenario Comparison** - Compare two different investment strategies side-by-side
- **Year-by-Year Table** - Detailed breakdown of growth over time
- **Milestone Markers** - Automatic annotations at key value thresholds
- **Dark/Light Theme** - Seamless theme switching with system preference detection
- **URL State Persistence** - Share exact calculations via URL parameters
- **Export Options** - Download data as CSV or JSON

### Sharing & Collaboration
- **Social Sharing** - One-click sharing to Twitter, Facebook, LinkedIn, Reddit
- **Email Sharing** - Generate formatted email with results
- **Copy Link** - Quick URL copying to clipboard

### User Experience
- **Keyboard Shortcuts** - Power user shortcuts for all major actions
- **Responsive Design** - Works beautifully on desktop, tablet, and mobile
- **Custom Design System** - Professional color palette with semantic tokens
- **Smooth Animations** - Polished transitions and micro-interactions

## Demo

Try it yourself: [Open Calculator](#)

## Screenshots

### Light Mode
![Light Mode](docs/images/light-mode.png)

### Dark Mode
![Dark Mode](docs/images/dark-mode.png)

### Scenario Comparison
![Comparison View](docs/images/comparison.png)

## Installation

### Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/cagr-calculator.git
   cd cagr-calculator
   ```

2. Open in your browser:
   ```bash
   open index.html
   ```

That's it! No build process, no dependencies to install.

### Deploy Anywhere

Since this is a single-file HTML application, you can deploy it to:
- **GitHub Pages** - Push to a `gh-pages` branch
- **Netlify** - Drag and drop the file
- **Vercel** - Deploy with zero configuration
- **Any web server** - Upload the HTML file

## Usage

### Basic Calculation

1. **Set Initial Investment** - Use the principal slider (1M - 50M)
2. **Choose Growth Rate** - Adjust the annual rate (1% - 20%)
3. **Select Time Period** - Pick years (10 - 100)
4. **View Results** - See instant calculations and chart updates

### Adding Contributions

1. **Set Contribution Amount** - Choose monthly/quarterly/annual amount
2. **Select Frequency** - Pick how often contributions are made
3. **See Impact** - Watch the chart update with contribution effects

### Comparing Scenarios

1. Click **"Compare Scenarios"**
2. Enter alternative parameters for Scenario B
3. View side-by-side comparison with difference calculations
4. See which strategy performs better over time

### Exporting Data

- **CSV Export** - `Ctrl/Cmd + E` or click "Export CSV"
- **JSON Export** - Click "Export JSON" for structured data
- **Share URL** - `Ctrl/Cmd + S` or click "Share" button

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + E` | Export as CSV |
| `Ctrl/Cmd + S` | Open share dialog |
| `Ctrl/Cmd + T` | Toggle year-by-year table |
| `Ctrl/Cmd + C` | Toggle scenario comparison |
| `Ctrl/Cmd + M` | Cycle theme mode |
| `Ctrl/Cmd + R` | Reset to defaults |
| `?` | Show keyboard shortcuts |
| `Esc` | Close share modal |

## Formula

The calculator uses the compound interest formula with contributions:

```
FV = PV × (1 + r)^t + PMT × [((1 + r)^t - 1) / r]
```

Where:
- **FV** = Future Value (ending amount)
- **PV** = Present Value (initial investment)
- **r** = Annual growth rate (as decimal)
- **t** = Time period in years
- **PMT** = Periodic payment (contribution amount × periods per year)

## Technology Stack

- **HTML5** - Semantic markup
- **CSS3** - Custom properties, grid, flexbox
- **Vanilla JavaScript** - No frameworks, pure ES6+
- **Chart.js** - Interactive charting library
- **Chart.js Annotation Plugin** - Milestone markers

## Design System

The calculator features a custom design system with:

- **Design Tokens** - Semantic color variables for easy theming
- **Typography System** - FKGroteskNeue font with Berkeley Mono for code
- **Spacing Scale** - Consistent 8px-based spacing system
- **Border Radius Scale** - Unified corner radius values
- **Shadow System** - Subtle elevation effects
- **Color Palette** - Teal primary with brown/gray neutrals

## Browser Support

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Opera 76+

## Configuration

### Customizing Defaults

Edit the `state` object in the `<script>` section:

```javascript
let state = {
    principal: 10000000,    // Initial investment
    rate: 0.10,            // 10% annual growth
    years: 50,             // 50 years
    contribution: 0,       // No contributions
    frequency: 'monthly'   // Monthly frequency
};
```

### Customizing Theme Colors

Modify CSS custom properties in the `:root` selector:

```css
:root {
    --color-primary: var(--color-teal-500);
    --color-background: var(--color-cream-50);
    /* ... more colors */
}
```

## API Reference

### URL Parameters

Share specific calculations using URL parameters:

```
?p=10000000&r=10.0&y=50&c=5000&f=monthly
```

| Parameter | Description | Example |
|-----------|-------------|---------|
| `p` | Principal amount | `10000000` |
| `r` | Growth rate (%) | `10.0` |
| `y` | Years | `50` |
| `c` | Contribution amount | `5000` |
| `f` | Frequency | `monthly` |

### JavaScript API

Access the calculator state programmatically:

```javascript
// Update state
state.principal = 20000000;
updateAll();

// Export data
const data = calculateGrowth(
    10000000,  // principal
    0.12,      // rate
    30,        // years
    5000,      // contribution
    'monthly'  // frequency
);

// Generate CSV
exportToCSV();

// Generate JSON
exportToJSON();
```

## Contributing

Contributions are welcome! Here's how you can help:

1. **Report Bugs** - Open an issue with detailed reproduction steps
2. **Suggest Features** - Share ideas for improvements
3. **Submit PRs** - Fork, create a feature branch, and submit a pull request

### Development Setup

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Test thoroughly
5. Commit: `git commit -m 'Add amazing feature'`
6. Push: `git push origin feature/amazing-feature`
7. Open a Pull Request

## Roadmap

- [ ] Add inflation adjustment calculator
- [ ] Support for tax calculations
- [ ] Historical data import
- [ ] PDF export with charts
- [ ] Multiple investment scenarios (3+)
- [ ] Monte Carlo simulation mode
- [ ] Portfolio diversification calculator
- [ ] Mobile app version

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- **Chart.js** - Beautiful JavaScript charting library
- **FKGroteskNeue** - Typography by FK Grotesk
- **Design Inspiration** - Modern financial tools and calculators

## Support

If you find this tool useful, please:
- ⭐ Star the repository
- 🐛 Report bugs and issues
- 💡 Suggest new features
- 📢 Share with others who might benefit

---

<div align="center">

Made with ❤️ for visualizing the power of compound growth

</div>
