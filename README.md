# KIPA Project – Waste Price Determinants Analysis

### Goal

The goal of this project is to identify correlations and patterns between waste prices and potential price determinants such as weather, energy, and business cycle factors.

### The `wPreis` Dataset

- Price of waste from around Sep 2020 until Sep 2023
- Could be negative (client received payment for waste) or positive (client paid for waste disposal)
- 10 unique clusters (collection of Postleitzahl) with 4 unique product categories
- No null values
- Correlations observed within categories in the same cluster

### Exploring Potential Price Determinants

#### Weather - First Approach

- Data extracted from an open meteo free API
- Parameters include temperature at 2 meters, wind speed at 10 meters, precipitation, rain, and snowfall
- Accessed using latitude and longitude of cities in each cluster

#### Weather - Second Approach

- Data obtained from Deutscher Wetterdienst (DWD), the German Meteorological Service
- Provides weather data dating back to the 1830s
- Parameters include temperature mean and max

#### Energy - Electricity

- Data from [netztransparenz.de](https://www.netztransparenz.de/EEG/Marktpraemie/Spotmarktpreis) (ct/kWh) for the whole of Germany from Jan 2021

#### Energy - Oil

- Global Oil and Gas Market Prices from Yahoo Finance used as proxy data
- **Adjusted Close Price (Adj Close)** considered for analysis

#### Energy - Gas

- Gas prices collected from Yahoo Finance for the whole of Germany
- Exploration of correlation with **Adjusted Close Price (Adj Close)**

#### Business Cycle - DAX

- DAX (Deutscher Aktien Index) data obtained from Yahoo Finance
- Calculated the adjusted close price of the weekly average for correlation analysis

#### Construction

- Data on construction permits number (per land per month) taken from Statistik der Baugenehmigungen (code 31111)

### Conclusions

- Weather determinants show very low correlation with waste prices
- Oil exhibits a significant correlation, around 0.6
- Gas shows lesser correlation than oil
- Electricity shows some high correlations, especially for certain lags
- Business Cycle (DAX) shows some significant inverse correlation
- Construction permits show high inverse correlation for some clusters

### Recommendations

- Avoid weather as a determinant due to low correlation
- Consider oil as a determinant but be mindful of major global events
- Further explore electricity as a determinant, especially for lags
- Consider DAX and Construction permits, noting the inverse correlation
- Avoid gas as a determinant due to lower correlation

