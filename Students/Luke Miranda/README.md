# Minnesota Agricultural Truck Routes

## Decision question

Which out-of-state markets should a Minnesota agricultural distributor evaluate first for a dedicated truck route?

## Public data source

- U.S. Bureau of Transportation Statistics, Freight Analysis Framework 6 (FAF6).
- [FAF6 Data Tabulation Tool](https://faf.ornl.gov/faf6/dtt_total.aspx)
- Downloaded November 12, 2026 as `faf_selected_subset.csv`. The export contains 402 rows and includes both Minnesota origin zones, truck shipments, and three agricultural commodity categories.
- Source fields are `dms_orig`, `dms_dest`, `sctg2`, `dms_mode`, and `million dollars in 2022`. The saved CSV combines destination zones by state and sums shipment values by commodity. Minnesota destinations are excluded. The source export does not identify the flow-type setting.

## Open the draft

Open `minnesota-truck-routes.html` in a browser. The chart works offline with an embedded copy of `minnesota-truck-shipments-2022.csv`. Use the dropdown to compare cereal grains, other agricultural products, and animal feed. The bars show estimated shipment value in millions of 2022 dollars.

## Data check

The chart uses real values from the downloaded FAF6 export. The aggregated figures were checked independently against the original rows. Iowa leads across the three included commodities and for cereal grains ($656.2956 million), while Wisconsin leads for animal feed ($882.1005 million). The initial HTML logic was also tested with synthetic rows, which are absent from the published data.

See [the AI log](ai-log.md) for the prompts and corrections.
