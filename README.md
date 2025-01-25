# 🍎 StockSearch-iOS

**Description:**  
StockSearch-iOS is a native iOS application built with **SwiftUI** and **WebKit**. It helps users track real-time stock information, manage a virtual stock portfolio, follow financial news, and analyze market trends. The app integrates with **Finnhub APIs** for live data and uses **MongoDB** for storing user data (favorites, portfolio, cash balance).

---

## Demo Video
- [Watch the Demo](https://drive.google.com/file/d/1RwTzVMQGPPdLmhJzjZISZDD7EmHEtHNV/view?usp=drive_link)

---

## Key Highlights

1. **SwiftUI 5 & MVVM:** Clean, declarative UI code and a scalable architecture.  
2. **Real-Time Data:** Fetches live quotes, news, and social sentiments via a Node.js backend.  
3. **Virtual Trading:** Simulates buying/selling stocks with a preset cash balance.  
4. **User-Friendly Features:** Customizable watchlist (Favorites), drag-and-drop reordering, and intuitive search.  
5. **Third-Party Libraries:**  
   - **Alamofire** for HTTP networking  
   - **SwiftyJSON** for JSON parsing  
   - **Kingfisher** for image downloading/caching  

---

## 1. Splash Screen & App Icon

When the user first launches the app, a **splash screen** is displayed, showcasing the app icon.

<p float="left">
  <img src="Screenshots/Appicon.jpg" alt="App Icon" width="200" />
  <img src="Screenshots/Splash%20Screen.jpg" alt="Splash Screen" width="200" />
</p>

---

## 2. Home Screen

The **Home Screen** is divided into two major sections: **Portfolio** and **Favorites**.

### 2.1 Portfolio Section
- **Cash Balance**: Shows uninvested cash (initially \$25,000).  
- **Net Worth**: Sum of Cash Balance and total stock holdings.  
- **Portfolio Stocks**: List of owned stocks with symbol, market value, total shares, and price change details.

<p float="left">
  <img src="Screenshots/Home%20Screen%20(Only%20Portfolio).jpg" alt="Home Screen (Only Portfolio)" width="230" />
  <img src="Screenshots/Home%20Screen%20(Portfolio%20and%20Favorites)%20.jpg" alt="Home Screen (Portfolio and Favorites)" width="230" />
  <img src="Screenshots/Home%20Screen%20(No%20Stocks).jpg" alt="Home Screen (No Stocks)" width="230" />
</p>

### 2.2 Favorites Section
- Displays a **watchlist** of user-favorite stocks.
- Shows **current price** and **price changes**, color-coded (green/red/gray).
- Allows **quick navigation** to detailed stock info.

<p float="left">
  <img src="Screenshots/Home%20Screen%20(Only%20Favorites).jpg" alt="Home Screen (Only Favorites)" width="230" />
</p>

### 2.3 Edit Mode & Deletions
Users can **edit** their watchlist or portfolio to reorder or delete entries:
- **Edit Mode** toggles the reordering handles and delete buttons.
- **Swipe to Delete** also supported on each row.

<p float="left">
  <img src="Screenshots/Edit%20Mode.jpg" alt="Edit Mode" width="200" />
  <img src="Screenshots/Move%20in%20Edit%20Mode.jpg" alt="Move in Edit Mode" width="200" />
</p>

<p float="left">
  <img src="Screenshots/Delete%20in%20Edit%20Mode.jpg" alt="Delete in Edit Mode" width="200" />
  <img src="Screenshots/Swipe%20to%20Delete.jpg" alt="Swipe to Delete" width="200" />
</p>

---

## 3. Search Functionality

A **search bar** at the top lets users look up stocks by symbol:
- **Autocomplete suggestions** appear as you type.
- Uses **debouncing** to reduce redundant backend calls.
- Redirects to the **Stock Details Screen** upon selecting a suggestion.

<p float="left">
  <img src="Screenshots/Search%20Functionality.jpg" alt="Search Functionality" width="250" />
</p>

---

## 4. Detailed Stock Information

Upon tapping a stock in **Home** or **Search**, users see a **Stock Details Screen**:

### 4.1 Stock Overview
- **Logo**, **company name**, **current price**, and **price changes** (with color-coding).
- **Favorite Icon** to add/remove from watchlist (with toast messages).

### 4.2 Stats & About
- **Stats**: High, Low, Open, and Previous Close.
- **About**: IPO date, industry, company website (clickable link), and peer symbols (scrollable).

<p float="left">
  <img src="Screenshots/Stats%20and%20About%20Section.jpg" alt="Stats and About Section" width="250" />
</p>

### 4.3 Charts (Hourly & Historical)
- Embedded **Highcharts** with **WKWebView** for interactive data visualization.
- **Hourly Chart** displays recent intraday trends.
- **Historical Chart** shows broader market history.

<p float="left">
  <img src="Screenshots/Stock%20Detail%20(Hourly).jpg" alt="Stock Detail (Hourly)" width="200" />
  <img src="Screenshots/Stock%20Detail%20(Historical).jpg" alt="Stock Detail (Historical)" width="200" />
</p>

### 4.4 Insights: Social Sentiments, Recommendation Trends, EPS Surprises
- **Social Sentiments**: Insider or social media sentiment data.
- **Recommendation Trends**: Analyst recommendations over time.
- **Historical EPS Surprises**: Past earnings performance vs. estimates.

<p float="left">
  <img src="Screenshots/Social%20Sentiments.jpg" alt="Social Sentiments" width="200" />
  <img src="Screenshots/Recommendation%20Trends.jpg" alt="Recommendation Trends" width="200" />
  <img src="Screenshots/Historical%20EPS%20Surprises.jpg" alt="Historical EPS Surprises" width="200" />
</p>

---

## 5. News Section

Displays news articles related to the chosen stock:
- **Large News Article** is shown as a featured item.
- **Small News Article** layout for the rest.

Clicking an article opens a **details sheet** with:
- Source, published date, title, and description.
- Link to open the full article in Safari.
- **Twitter** and **Facebook** buttons for sharing.

<p float="left">
  <img src="Screenshots/Large%20News%20Article.jpg" alt="Large News Article" width="200" />
  <img src="Screenshots/Small%20News%20Article.jpg" alt="Small News Article" width="200" />
</p>

<p float="left">
  <img src="Screenshots/News%20Details.jpg" alt="News Details" width="200" />
  <img src="Screenshots/Facebook.jpg" alt="Facebook Share" width="200" />
  <img src="Screenshots/Twitter.jpg" alt="Twitter Share" width="200" />
</p>

---

## 6. Portfolio Management & Trading

### 6.1 Portfolio Screen
- Shows **Stocks Owned** with average cost, total cost, market value, price changes.
- If **no stocks** are owned, displays a prompt message.

<p float="left">
  <img src="Screenshots/Portfolio%20when%20stocks%20are%20owned.jpg" alt="Portfolio (Stocks Owned)" width="230" />
  <img src="Screenshots/Portfolio%20when%20no%20stocks%20are%20owned.jpg" alt="Portfolio (No Stocks Owned)" width="230" />
</p>

### 6.2 Trade Sheet
- Users can buy or sell shares via a **sheet** overlay.
- Validates:
  - Sufficient funds for buying.
  - Sufficient shares for selling.
  - Positive and valid input.

<p float="left">
  <img src="Screenshots/Trade%20Sheet%201.jpg" alt="Trade Sheet 1" width="230" />
  <img src="Screenshots/Trade%20Sheet2.jpg" alt="Trade Sheet 2" width="230" />
</p>

#### Trade Success Messages
- Different messages for **buy/sell** and single vs. multiple shares.

<p float="left">
  <img src="Screenshots/Trade%20Success%20Message1.jpg" alt="Trade Success Message 1" width="230" />
  <img src="Screenshots/Trade%20Success%20Message2.jpg" alt="Trade Success Message 2" width="230" />
</p>

---

## 7. Fetching Data & Loading States

Whenever the app retrieves fresh data (e.g., on screen load), a **ProgressView** shows a "Fetching Data" message.

<p float="left">
  <img src="Screenshots/Fetching%20Data.png" alt="Fetching Data" width="230" />
</p>

---

## Technologies & Architecture

- **SwiftUI 5** + **MVVM** for a clean, reactive UI  
- **Node.js** backend for API calls to Finnhub and MongoDB  
- **MongoDB** to store favorites, portfolio, and cash balance  
- **SF Symbols** for consistent iconography  

---

## Challenges Faced

1. **Asynchronous Data & Performance**  
   Used `@Published` properties, debouncing, and background threads to ensure smooth UI updates.

2. **WKWebView Integration**  
   Bridged SwiftUI and UIKit to embed **Highcharts** for hourly/historical stock data.

3. **Robust Error Handling**  
   Handled invalid inputs, insufficient funds/shares, and network errors without crashing.

---

## Conclusion

**StockSearch-iOS** showcases my ability to create a production-ready iOS application with SwiftUI, leveraging real-time data and user-focused features. It integrates a robust backend (Node.js & MongoDB), provides a smooth user experience (animations, error handling, and data caching), and supports essential stock-tracking functionalities.

Feel free to reach out if you have any questions or would like access to the source code:

**Contact:** [bafnashubham16@gmail.com](mailto:bafnashubham16@gmail.com)
