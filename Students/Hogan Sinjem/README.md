[README.md](https://github.com/user-attachments/files/35112026/README.md)[Uplo# Hogan Sinjem — UNFI Winter Delivery Planning

## Decision question

**Should UNFI adjust its delivery schedules during severe Minnesota winter weather to avoid delays and reduce transportation costs?**

This project uses historical weather observations near Minneapolis–Saint Paul to identify periods when weather may create delivery-planning risk. The analysis supports a **targeted, weather-triggered flexibility approach**, rather than changing every winter delivery schedule.

## Project files

```text
Hogan_Sinjem/
├── README.md
├── ai-log.md
├── index.html
└── weather_daily_summary.csv
```

- `README.md` — project question, source, methodology, findings, limitations, and usage.
- `ai-log.md` — record of the AI-assisted work, including known prompts, decisions, corrections, and checks.
- `index.html` — self-contained interactive dashboard. It embeds the daily data and works offline.
- `weather_daily_summary.csv` — the 365 daily records used by the dashboard.

## Public data source

The uploaded dashboard identifies **Open-Meteo** as the source and describes the original data as hourly historical weather observations for:

- **Coordinates:** 44.956062° N, 93.20929° W
- **Elevation:** 261 meters
- **Time zone:** America/Chicago
- **Period:** January 1–December 31, 2025
- **Variables identified in the uploaded dashboard:** time, temperature at 2 meters, snowfall, and snow depth.

Open-Meteo Historical Weather API: https://open-meteo.com/en/docs/historical-weather-api

The Open-Meteo documentation explains that its historical weather service uses weather reanalysis datasets. The coordinate is one point near Minneapolis–Saint Paul; it is not a statewide or county-by-county sample.

**Important source-file note:** The file attached for this project was an HTML dashboard containing 365 daily summaries in its JavaScript—not the original hourly CSV named inside that dashboard (`open-meteo-44.96N93.21W261m.csv`). The CSV in this folder was created by extracting those exact embedded daily records. It is therefore a transparent export of the data available in the attachment, not a replacement claim that the missing hourly source file was supplied.

## Methodology

The uploaded dashboard describes the daily calculations as follows:

1. **Daily snowfall (`snowfall_in`):** sum of hourly snowfall readings for each date, in inches.
2. **Average daily temperature (`avg_temp_f`):** mean of hourly 2-meter temperature readings for each date, in degrees Fahrenheit.
3. **Maximum daily snow depth (`max_snow_depth_ft`):** largest hourly snow-depth reading for each date, in feet.
4. **Freezing hours (`freezing_hours`):** count of hourly temperature readings at or below 32°F for each date.

The daily CSV includes `date`, `month`, `year`, `avg_temp_f`, `snowfall_in`, `max_snow_depth_ft`, and `freezing_hours`. The dashboard filters the records by month, lets the user choose the daily chart measure, and includes a user-adjustable snowfall threshold for counting days that meet or exceed that amount. The monthly snowfall chart is calculated from the daily CSV in the browser.

### Verification performed

The exported data was checked independently for:

- 365 records covering every date from 2025-01-01 through 2025-12-31;
- no duplicate dates;
- no missing values in the seven exported columns;
- daily freezing-hour values within the possible 0–24 range;
- annual and monthly totals, averages, and maximums recalculated from the exported CSV.

The checks verify the extracted daily records and calculations made from them. Because the original hourly CSV was not attached, the hourly-to-daily aggregation itself could not be independently reconstructed or audited.

## Key findings from the attached daily records

| Measure | Result |
|---|---:|
| Daily records | 365 |
| Total snowfall in 2025 | 31.242 inches |
| Average of daily average temperatures | 46.88°F |
| Total hours at or below 32°F | 2,327 |
| Days with measurable snowfall | 50 |
| Days with at least 1 inch of snowfall | 8 |
| Maximum daily snow depth | 0.853 feet (10.236 inches) |
| Largest daily snowfall | 4.216 inches on March 5, 2025 |

### Snowfall by month

| Month | Snowfall |
|---|---:|
| January | 1.719 in |
| February | 3.871 in |
| March | 7.414 in |
| April | 2.207 in |
| November | 5.514 in |
| December | 10.517 in |

May through October recorded zero snowfall in the attached daily data. December had the highest monthly snowfall total. The maximum recorded daily snow depth was 0.853 feet on December 10, 2025.

## Decision implications for UNFI

The observations support monitoring weather conditions and allowing **targeted delivery flexibility** when forecasts indicate disruptive snowfall or extended freezing conditions. Potential actions to evaluate include adjusting dispatch timing, widening delivery windows, coordinating with carriers and receiving sites, or rescheduling affected routes.

The dataset **does not establish** that any specific schedule change will prevent delays or reduce costs. It contains no UNFI shipment records, delivery performance, road conditions, carrier rates, fuel use, route miles, labor costs, rescheduling costs, inventory effects, or spoilage. A cost-saving conclusion requires those operational data.

A useful next step would be a pilot comparing on-time delivery, miles driven, fuel, carrier wait time, rescheduling expense, labor, inventory, and spoilage before and after weather-triggered changes.

## How to use the interactive webpage

1. Open `index.html` in a modern web browser. No installation, server, internet connection, or external chart library is required.
2. Select **All of 2025** or a month.
3. Choose a daily chart measure: snowfall, average temperature, maximum snow depth, or freezing hours.
4. Move the snowfall threshold slider to change which dates are flagged on the daily chart and counted in the KPI.
5. Hover over (or tap) chart points and bars to inspect their values.
6. Read the decision takeaway and limitations before drawing conclusions about UNFI transportation costs.

The dashboard embeds the same daily observations as the CSV so it can run offline. The CSV is included separately for review, reuse, and upload to GitHub.

## Scope and limitations

- One coordinate near Minneapolis–Saint Paul; not representative of every Minnesota county or UNFI route.
- One calendar year (2025); one year cannot establish long-term winter patterns.
- Weather observations are not actual road conditions or delivery outcomes.
- No crop or agricultural production variables are included.
- No UNFI transportation or cost records are included.
- The hourly source CSV was referenced by the uploaded dashboard but was not included in the attachment. The daily values are extracted from the uploaded HTML and not re-aggregated from hourly observations.

## References

- Open-Meteo, Historical Weather API: https://open-meteo.com/en/docs/historical-weather-api
- Uploaded project artifact: `unfi_minnesota_winter_delivery_analysis(1).html` (source for the embedded daily observations and the stated source metadata).
ading README.md…]()

