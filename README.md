# smk-mrdt

An interactive map application for looking up Municipal Regional District Tax (MRDT) rates for properties across British Columbia. Built with [SMK (Server Map Kit)](https://github.com/bcgov/smk) and powered by [Leaflet](https://leafletjs.com/).

## Overview

The MRDT Lookup Tool provides BC residents and property managers with an easy-to-use web-based map interface to determine the applicable Municipal Regional District Tax rate for any property location in the province. The application displays MRDT jurisdictions with their corresponding tax rates, accommodation areas, and implementation dates.

### About MRDT

The Municipal Regional District Tax (MRDT) is a tax levied on short-term rental accommodations in designated areas of British Columbia. This tool helps property owners, managers, and renters understand which tax rates apply to specific locations.

## Features

- **Interactive Map Interface**: Zoom and pan across British Columbia to explore MRDT designations
- **Multiple Tax Rates**: Display of both 2% and 3% MRDT zones
- **Property Information**: Click on any jurisdiction to view:
  - Tax recipient municipality
  - Applicable tax rate
  - Accommodation area designation
  - MRDT start and repeal dates
- **Responsive Design**: Works on desktop and mobile devices
- **Geospatial Data**: Based on accurate GeoJSON boundaries of MRDT jurisdictions

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or higher)
- npm (comes with Node.js)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/bcgov/smk-mrdt.git
   cd smk-mrdt
   ```

2. Install dependencies:
   ```bash
   npm install
   ```
   
   This will automatically apply any necessary patches via `patch-package`.

### Running Locally

To view and test the application locally:

```bash
npm run view
```

This will:
- Start a local HTTP server on port 8080
- Automatically open the application in your default browser

Access the application at `http://localhost:8080`

## Project Structure

```
smk-mrdt/
├── index.html              # Main HTML entry point
├── smk-init.js             # SMK initialization script
├── smk-config.json         # Map configuration and layer definitions
├── package.json            # Node.js dependencies and scripts
├── Dockerfile              # Container build configuration
├── LICENSE                 # Apache 2.0 License
├── code_of_conduct.md      # Community guidelines
├── README.md               # This file
├── assets/
│   └── style.css           # Custom styling
├── layers/
│   ├── two-percent.geojson # 2% MRDT zones
│   ├── three-percent.geojson# 3% MRDT zones
│   └── smk-catalog.json    # Layer catalog configuration
└── patches/
    └── @bcgov+smk+1.2.3.patch # Patches applied to SMK dependency
```

## Configuration

The application is configured through `smk-config.json`, which defines:

- **Map Viewer**: Leaflet-based viewer with initial zoom level and extent centered on BC
- **Base Map**: Streets basemap from ESRI
- **Layers**: Vector layers for 2% and 3% MRDT zones with custom styling
- **Styling**: Orange borders (#d95f02) to highlight MRDT jurisdictions
- **Attributes**: Display of tax rates, recipients, accommodation areas, and dates


## Data Sources

- **MRDT Boundaries**: GeoJSON files containing jurisdictional boundaries
- **Base Maps**: ESRI Maps (requires valid ESRI API key in configuration)

## Technologies Used

- **[SMK (Server Map Kit)](https://github.com/bcgov/smk)**: v1.2.4 - BC Government's map framework
- **[Leaflet](https://leafletjs.com/)**: Open-source mapping library
- **[GeoJSON](https://geojson.org/)**: Geographic data format
- **[Caddy](https://caddyserver.com/)**: Lightweight web server
- **[Node.js](https://nodejs.org/)**: JavaScript runtime


## License

Licensed under the Apache License, Version 2.0. See the [LICENSE](LICENSE) file for details.

