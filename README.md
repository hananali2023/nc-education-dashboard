# North Carolina Education Dashboard
**Exploring Racial Disparities in Public School Expenditure Across NC Counties**
 
## Overview
 
An interactive data visualization dashboard analyzing the relationship between school funding, student diversity, and academic achievement across all 100 North Carolina counties. Built with D3.js, the dashboard links a choropleth county map, a racial demographics bar chart, and scatter plots which all updates simultaneously when a county is selected.
 
**Research Question:** Does diversity correlate with academic achievement and school funding in North Carolina public schools?
 
## Live Demo
 
Open `index.html` in a local server (see [Setup](#setup) below).
 
## Features
 
- **Interactive NC County Map** — click any county to update all visualizations
- **Racial Demographics Bar Chart** — shows student population breakdown by race for the selected county
- **Linked Scatter Plots** — public school expenditure vs. diversity index, and academic achievement vs. diversity index
- **Tooltips** — hover over any county or bar for detailed statistics
- **County Dropdown** — alternative selection method synced with the map
## Dashboard Preview
 
The dashboard allows users to answer questions like:
- How does Durham County's per-student expenditure compare to neighboring counties?
- Which counties have the highest diversity index alongside strong academic outcomes?
- Where does funding correlate (or not) with student achievement?
## Data Sources
 
| Dataset | Source | Variables Used |
|---------|--------|---------------|
| MyFutureNC County Data | [MyFutureNC Dashboard](https://dashboard.myfuturenc.org/county-data-and-resources/) | Racial demographics, graduation rates, college readiness, expenditure per student, diversity index |
| NC Population Data | NC County Data (internal) | Population (2022), growth rate, population density |
| Public School Expenditures | [NC Office of State Budget and Management](https://linc.osbm.nc.gov) | County-level public school expenditure (2021) |
| County Boundaries | US Census Bureau (TopoJSON) | NC county geographic boundaries |
 
## Diversity Index
 
The diversity index used in this project was calculated using the **Shannon-Wiener model**: a standard ecological diversity metric adapted for racial demographics. It accounts for both the number of racial groups present and the evenness of their distribution within a county's student population. See the [Shannon-Wiener methodology](https://archives.huduser.gov/healthycommunities/sites/default/files/public/Racial%20Diversity%20using%20Shannon-Wiener%20Index.pdf) for details.
 
## File Structure
 
```
nc-education-dashboard/
├── index.html          # Main dashboard
├── report.html         # Full project report and methodology
├── map.js              # D3 choropleth map (NC_Map class)
├── bargraph.js         # D3 bar chart (BarGraph class)
├── data/
│   ├── myfuturenc.csv      # Primary dataset (demographics, expenditure, outcomes)
│   ├── nc_county_data.csv  # Population and density data
│   ├── nc-counties.json    # TopoJSON county boundaries
│   └── education.csv       # Public school expenditure by county (OSBM)
└── README.md
```
 
## Setup
 
Because this project loads local CSV and JSON files, it needs to run on a local server (browsers block file:// requests for security).
 
**Option 1 — Python (recommended):**
```bash
cd nc-education-dashboard
python3 -m http.server 8000
# Then open http://localhost:8000 in your browser
```
 
**Option 2 — VS Code Live Server:**
Install the Live Server extension, right-click `index.html`, and select "Open with Live Server."
 
## Tech Stack
 
- **D3.js v7** — map projection, scales, data binding, transitions
- **TopoJSON** — county boundary rendering
- **Tippy.js** — tooltip library
- **Vanilla JavaScript** — class-based architecture with D3 dispatch for cross-component communication
## Team
 
Ian Elliott, Neha Patel, Jay Saini, Hanan Ali  
*INLS 641: Visual Analytics — University of North Carolina at Chapel Hill*
 
