# Paris Airbnb Listings – Market and Geospatial Analysis

This repository presents an exploratory analysis of **64,690 Paris Airbnb listings**. It examines how advertised nightly prices vary by neighbourhood and guest capacity, and uses an interactive map to show where higher- and lower-priced neighbourhoods sit within the city.

The project demonstrates how **market segmentation and geospatial visualization** can help benchmark short-term rental prices and identify patterns worth investigating.

---

## Project Overview

- Filter the dataset to Paris and inspect missing signup dates, zero prices and zero-capacity entries.
- Compare average nightly prices across neighbourhoods and guest capacities.
- Geocode neighbourhoods and map their average prices using an interactive Plotly map.
- Group listings by their hosts' signup year and compare listing counts and average prices across those groups.

---

## Analysis Approach

- **Neighbourhood pricing:** Rank neighbourhoods by mean nightly price and visualize the differences in a horizontal bar chart.
- **Geospatial visualization:** Use geopy and Nominatim to obtain a point for each neighbourhood. Map markers encode average nightly price through colour and size.
- **Guest capacity:** Compare average nightly prices by the number of guests a listing accommodates, with a separate look at capacity within Élysée.
- **Host signup year:** Compare listings associated with hosts who joined in different years using the nightly prices recorded in the dataset.

---

## Key Findings

- **Élysée had the highest average nightly price** at approximately **€211**, followed by Louvre at **€175**. Ménilmontant had the lowest average at approximately **€75**.
- **Several higher-priced neighbourhoods appear around central and western Paris** on the map. The pattern raises a follow-up question about whether proximity to attractions is associated with pricing after accounting for factors such as guest capacity.

---

## Limitations and Scope

- Neighbourhood averages reflect the mix of listings in each area. Differences in capacity, property type and other listing characteristics can affect comparisons.
- Zero-value entries are retained in the analysis, and unusually high prices can influence the mean.
- The map shows one geocoded point per matched neighbourhood. Neighbourhoods without a match are omitted from the map.
- The final chart groups **listing rows by host signup year**. A host with multiple listings can contribute multiple rows. Each group's average reflects prices recorded in the dataset, so the chart cannot establish historical price changes or the effect of regulation.

---

## Dataset and Setup

The notebook reads `Listings.csv` and uses the `city`, `host_since`, `neighbourhood`, `accommodates` and `price` columns.

1. Place `Listings.csv` in the same directory as the notebook.
2. Install the dependencies:

   ```bash
   python -m pip install jupyter pandas==2.2.3 matplotlib seaborn geopy "plotly>=5.24"
   ```

3. Open the notebook in Jupyter and run the cells in order. Geocoding and loading the interactive basemap require internet access.

---

## Intended Audience and Use

This project is part of my **marketing analytics portfolio**. It shows how I use Python to compare segments within a local market, communicate geographic pricing patterns and frame follow-up questions for further analysis.
