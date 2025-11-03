# Bitasmbl-Crypto-Price-Tracker

Description
A sleek React application that tracks live cryptocurrency prices using the CoinGecko API. It allows users to search and view details of top cryptocurrencies, including name, symbol, current price, and price change percentage. This project focuses on API integration, dynamic table rendering, and a clean responsive UI built with Tailwind CSS.

## Tech Stack
- React
- Tailwind CSS

## Requirements
- Use React hooks for state and effects
- Fetch live cryptocurrency data from CoinGecko API
- Implement search and filter functionality
- Style the UI using Tailwind CSS for a responsive layout

## Installation
1. Clone the repository:
   bash
   git clone https://github.com/your-username/Bitasmbl-Crypto-Price-Tracker.git
   
2. Navigate into the project directory:
   bash
   cd Bitasmbl-Crypto-Price-Tracker
   
3. Install dependencies:
   bash
   npm install
   
4. (Optional) Create a `.env` file in the root directory to override the API base URL:
   env
   REACT_APP_API_BASE_URL=https://api.coingecko.com/api/v3
   
5. Start the development server:
   bash
   npm start
   

## Usage
1. Open your browser and go to `http://localhost:3000`.
2. Use the search bar at the top to filter cryptocurrencies by name or symbol.
3. View live updates of current price, 24h price change percentage, and market data in a responsive table.
4. The table layout adapts to mobile and desktop viewports with Tailwind CSS.

## Implementation Steps
1. Initialize the project with Create React App:
   bash
   npx create-react-app .
   
2. Install and configure Tailwind CSS:
   bash
   npm install -D tailwindcss postcss autoprefixer
   npx tailwindcss init -p
   
   Configure `tailwind.config.js` and include Tailwind directives in `src/index.css`.
3. Create a component structure:
   - `components/SearchBar.jsx`
   - `components/CryptoTable.jsx`
   - `App.jsx`
4. In `App.jsx`, use `useState` and `useEffect` hooks to fetch data from the CoinGecko API endpoint:
   js
   const API_URL = process.env.REACT_APP_API_BASE_URL || 'https://api.coingecko.com/api/v3';
   useEffect(() => {
     fetch(`${API_URL}/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=50&page=1&sparkline=false`)
       .then(res => res.json())
       .then(data => setCoins(data));
   }, []);
   
5. Implement search and filter logic in `App.jsx`, passing filtered data down to `CryptoTable`.
6. Build `CryptoTable.jsx` to render a responsive table with Tailwind CSS utility classes.
7. Style `SearchBar.jsx` with Tailwind CSS input components for mobile and desktop.
8. Test responsiveness and cross-browser compatibility.
9. Commit changes and push to GitHub.

## API Endpoints
- GET /coins/markets?vs_currency=usd&order=market_cap_desc&per_page=50&page=1&sparkline=false