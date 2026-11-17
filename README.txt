KENYA DONOR PROJECTS MAP
========================

index.html                   the map page (settings are at the top of the script, in CONFIG)
data/projects.csv            the project list: edit this to add projects or mark them completed
data/county_centres.csv      where each county's dots are drawn
data/kenya_counties.geojson  county boundaries (OpenStreetMap contributors)
lib/                         Leaflet 1.9.4 and PapaParse 5.4.1 (bundled, with their licences)

To view on your computer:  open a terminal in this folder, run   python -m http.server 8000
                           then go to http://localhost:8000
To publish:                upload the whole folder to GitHub Pages or Netlify (see the guide).

projects.csv columns (one row per project, per financial year, per donor, per loan/grant):
  project_id        unique ID for the row (e.g. R0484 for a new row)
  project_key       same key for every row of the same project (links years together)
  project_name      name shown on the map
  category          Project or Programme  (drives the "Map shows" filter)
  financial_year    e.g. 2025/26
  sector            Health, Water or Infrastructure (a new sector gets grey unless added to CONFIG)
  donor             e.g. World Bank (IDA)
  funding_type      Loan or Grant
  amount_ksh        allocation for that year, whole shillings, no commas needed
  completion_year   e.g. 2027 (blank if unknown)
  status            Ongoing, Completed, Planned, Cancelled or Not stated  (Completed = ring on the map)
  status_note       free text, optional
  counties          one or more county names separated by ;   or National   or blank (not specified)
  latitude/longitude optional exact location; if filled, the dot is drawn there instead of the county centre

Save from Excel as  "CSV UTF-8 (Comma delimited)".
