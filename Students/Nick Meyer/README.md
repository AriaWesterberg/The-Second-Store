# Minnesota Corn Harvest: Where to Send Trucks and Storage

## Decision question

Which Minnesota counties should we send the most trucks and storage space to during this year's corn harvest?

## Public data source

- U.S. Department of Agriculture, National Agricultural Statistics Service (NASS), [Quick Stats](https://quickstats.nass.usda.gov/).
- Query: SURVEY › CROPS › FIELD CROPS › CORN › `CORN, GRAIN - PRODUCTION, MEASURED IN BU` › COUNTY › MINNESOTA.
- Fields used: Year, County, Value (corn for grain production in bushels).
- The 2021–2023 county values were copied from the NASS Minnesota Corn County Estimates reports, which publish the same county numbers as Quick Stats:
  - [February 2023 report](https://www.nass.usda.gov/Statistics_by_State/Minnesota/Publications/County_Estimates/2023/MN-CtyEst-Corn-02-23.pdf) (2021 and 2022)
  - [February 2024 report](https://nass.usda.gov/statistics_by_state/Minnesota/Publications/County_Estimates/2024/MN-CtyEst-Corn-02-24.pdf) (2022 and 2023)
- Retrieved November 12, 2026. Quick Stats itself could not be reached from the AI assistant's workspace, so the data was not exported from Quick Stats directly.
- Saved as `mn-corn-grain-production-by-county.csv`: 211 rows with the columns `year`, `county`, `ag_district` and `corn_grain_bushels`. NASS withholds some counties in some years, mostly to protect individual farms' privacy. Those bushels appear only in the `Other (combined) counties` row.
- The statewide planning number, 1,696,440,000 bushels, is Minnesota's 2025 corn-for-grain total from the [NASS 2025 State Agriculture Overview](https://www.nass.usda.gov/Quick_Stats/Ag_Overview/stateOverview.php?state=MINNESOTA).

## Open the page

Open `mn-corn-harvest-trucks-storage.html` in a browser. It works offline because a copy of the CSV is built into the page. When the folder is hosted on GitHub Pages, the page reads `mn-corn-grain-production-by-county.csv` from the folder instead and confirms it matches the built-in copy.

- **Year:** one year, or the average of all three.
- **County:** "All counties" shows the ranking. Picking a county shows its production by year.
- **Counties shown:** a slider for how many counties the chart shows (5–40).
- **2026 statewide crop, share hauled, bushels per truckload:** planning inputs. Change them and every estimate updates.
- Hover over a bar for details, or click it to open that county's history. The planning table below the chart can be downloaded as a CSV.
- **Load a Quick Stats CSV:** adds newer years (2024, 2025) from a Quick Stats export for the current visit.

## Methodology

1. For each county, average its production over the selected years, counting only the years NASS published.
2. Divide by the Minnesota total for those same years to get the county's share of the state crop.
3. Estimated 2026 bushels = share × the statewide planning number.
4. Truckloads = estimated bushels × share hauled ÷ bushels per truckload. Storage needed = estimated bushels × share hauled.
5. Rank counties by share. Defaults: 1,000 bushels per semi load and 100% hauled at harvest.

## Key findings

Using the average of 2021–2023 and the default planning inputs:

| Rank | County | Ag district | Avg production (bu) | Share of state | Est. 2026 bu | Truckloads |
|---|---|---|---|---|---|---|
| 1 | Renville | Central | 50,211,333 | 3.45% | 58,589,885 | 58,590 |
| 2 | Martin* | South Central | 42,753,500 | 3.00% | 50,928,996 | 50,929 |
| 3 | Redwood | Southwest | 42,408,667 | 2.92% | 49,485,221 | 49,485 |
| 4 | Faribault* | South Central | 41,197,000 | 2.89% | 49,074,856 | 49,075 |
| 5 | Nobles | Southwest | 38,765,000 | 2.67% | 45,233,551 | 45,234 |
| 6 | Mower* | Southeast | 39,484,500 | 2.66% | 45,048,059 | 45,048 |
| 7 | Jackson | Southwest | 38,085,000 | 2.62% | 44,440,082 | 44,440 |
| 8 | Freeborn | South Central | 37,599,667 | 2.59% | 43,873,763 | 43,874 |
| 9 | Blue Earth | South Central | 37,300,333 | 2.57% | 43,524,482 | 43,524 |
| 10 | Swift* | West Central | 35,869,500 | 2.41% | 40,923,688 | 40,924 |

\* Published for only two of the three years.

- **Send the most trucks and storage to Renville County.** It was the top producer in all three years (43.2M, 52.9M and 54.6M bushels) and has the largest share of the state crop.
- The top 10 counties hold about **27.8%** of Minnesota's corn crop: about **471 million bushels**, or **471,123 truckloads** at the default settings.
- The crop is concentrated in the south and west. Of all the bushels credited to named counties in 2021–2023, the South Central district had 22.6%, West Central 19.6%, Southwest 19.1% and Central 17.8%. North Central had 0.1%.
- Martin and Faribault rank 2nd and 4th, but NASS withheld their 2023 numbers. Their ranks rest on 2021–2022 only.

## Data check

- For every year, the county values plus `Other (combined) counties` add up exactly to NASS's published Minnesota totals: 1,387,680,000 (2021), 1,460,550,000 (2022) and 1,513,300,000 (2023) bushels.
- The 2022 values appear in both NASS reports and match.
- The 2023 top five (Renville 54.6M, Redwood 41.9M, Jackson 39.1M, Swift 38.8M, Nobles 38.5M) match the text of the February 2024 NASS report.
- A separate Python script recalculated every county's share and 2026 estimate from the CSV. All 80 counties matched the page's table, both opened offline and served from a web server.
- The webpage was tested once with a made-up CSV to check the upload button. That test file is not part of this folder or the page.

## Limitations

- County numbers for the 2024 and 2025 crops are not included yet.
- This year's weather by county, existing elevator and bin capacity, and local prices are not modeled.
- The 2026 statewide number is a stand-in (the 2025 total). Replace it with USDA's latest forecast.

See [the AI log](ai-log.md) for the prompts, errors and checks.
