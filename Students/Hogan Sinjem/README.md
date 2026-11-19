[README (1).md](https://github.com/user-attachments/files/35112096/README.1.md)[Upl# UNFI Minnesota Winter Delivery Planning

## Decision question

Should UNFI adjust its delivery schedules during severe Minnesota winter weather to avoid delays and reduce transportation costs?

## Public data source

- Open-Meteo, Historical Weather API.
- Weather observations for a location near Minneapolis–Saint Paul (44.956062° N, 93.20929° W; elevation 261 m).
- The data covers January 1–December 31, 2025, in the America/Chicago time zone.
- The uploaded HTML dashboard contained 365 daily weather records. The original hourly CSV referenced in that dashboard was not included with the upload.
- The `weather_daily_summary.csv` file contains the daily records extracted from the uploaded HTML: date, average temperature, snowfall, maximum snow depth, and freezing hours.
- Source documentation: [Open-Meteo Historical Weather API](https://open-meteo.com/en/docs/historical-weather-api).

## Open the draft

Open `index.html` in a browser. The interactive dashboard works offline and does not require an installation or external libraries. Use the month dropdown to filter the year, choose a weather measure for the daily chart, and adjust the snowfall threshold to see which days meet the selected amount. The dashboard also displays monthly snowfall totals and summary measures.

## Data check

The dashboard uses the 365 daily records extracted from the uploaded HTML file. The CSV was checked for complete date coverage from January 1 through December 31, 2025, duplicate dates, missing values, and valid daily freezing-hour values (0–24). Annual and monthly summary calculations were also checked against the exported CSV.

Key results from the daily records:

- Total snowfall: **31.242 inches**.
- Days with measurable snowfall: **50**; days with at least 1 inch: **8**.
- Highest monthly snowfall: **December, 10.517 inches**.
- Largest daily snowfall: **4.216 inches on March 5, 2025**.
- Total freezing hours: **2,327**.

These observations can help UNFI evaluate targeted weather-related delivery flexibility. They do not prove that schedule changes will reduce delays or transportation costs because the dataset does not include UNFI shipments, route conditions, delivery performance, or transportation expenses. The data represents one location and one year, not all of Minnesota.

See the [AI log](ai-log.md) for the prompts, project decisions, data checks, and limitations.
oading README (1).md…]()
