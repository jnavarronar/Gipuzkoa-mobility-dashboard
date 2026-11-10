# Gipuzkoa Mobility Dashboard

Interactive web app that analyses public bus efficiency in San Sebastián and road traffic across Gipuzkoa (Basque Country), and recommends whether a bus trip is faster by bike. Built with Python and Streamlit.

🏆 **Winning project of the Computer Science Challenge (Reto) at Tecnun – University of Navarra, awarded Matrícula de Honor.** Team project developed in collaboration with the MIT City Science Lab.

🔗 **Live demo:** [gipuzkoa-mobility-dashboard.streamlit.app](https://gipuzkoa-mobility-dashboard.streamlit.app)

## Key findings
- **Bus network:** about 38% of stop-to-stop bus segments in San Sebastián run below 15 km/h, a typical urban cycling speed. On those segments, cycling is a realistic and faster alternative.
- **Road traffic:** traffic across Gipuzkoa's monitoring stations peaks in the afternoon (14:00–19:00). The busiest hour carries over 20 times the traffic of the quietest one (around 04:00).
- Combining bus schedules with road-traffic counts shows where and when congestion builds up, and supports data-driven decisions on transport planning.

## Features
| Page | What it does |
|---|---|
| **Bus Stations** | Descriptive statistics and boxplots of travel time and average speed between stops, by route, day of the week and stop. |
| **Interactive Map** | Map of all bus stops and routes, plus an hourly heat map of average bus speed per route to locate delays. |
| **Traffic Networks** | Traffic distribution per station, hourly/weekly/monthly/seasonal patterns, multi-year trends with confidence intervals, and a map of monitoring stations. |
| **Time Efficiency** | Route recommender: pick a bus route and two stops, and the app compares the segment's average bus speed with a 15 km/h cycling benchmark to suggest bus or bike. |

## Data
| Dataset | Source | Scale |
|---|---|---|
| Dbus (San Sebastián city buses), GTFS schedules | [Open Data Euskadi – MoveUskadi](https://opendata.euskadi.eus/catalogo/-/moveuskadi-datos-de-la-red-de-transporte-publico-deeuskadi-operadores-horarios-paradas-calendario-tarifas-etc/) | 536 stops, 11,118 trips, ~188,000 stop times |
| Road traffic counts (light and heavy vehicles, hourly) | [Gipuzkoa Irekia open data](https://www.gipuzkoairekia.eus/es/datu-irekien-katalogoa/-/openDataSearcher/search/true) | 221 monitoring stations, 60 weekly samples (2020–2024), ~805,000 hourly records |

## Tech stack
Python · Pandas · NumPy · Plotly · Matplotlib · Seaborn · Folium · geopy · Streamlit

## How to run
```bash
git clone https://github.com/jnavarronar/gipuzkoa-mobility-dashboard.git
cd gipuzkoa-mobility-dashboard
pip install -r requirements.txt
streamlit run Pagina_Principal.py
```

## Project structure
```
Pagina_Principal.py      # Main page and navigation
pages/
  Bus_Stations.py        # Bus travel time and speed analysis
  Interactive_map.py     # Stops map and speed heat map
  Traffic_networks.py    # Road traffic analysis
  Time_efficiency.py     # Bus vs. bike recommender
Datos 1/                 # Dbus GTFS data
Datos 2/                 # Weekly traffic counts and station locations
```

## Team
Samuel Jiménez · Kerman Martin · Jose Francisco Navarro · Juan Pablo Queralt · Roberto Rubio

## My role
- Coordinated the team and integrated each member's components into a single working application.
- Designed and built the Streamlit dashboard (layout, navigation, interactive maps and visualizations).
