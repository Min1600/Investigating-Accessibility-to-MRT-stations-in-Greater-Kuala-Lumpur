# Pedestrian Access to MRT Kajang Line Stations

Measuring how direct the walk to each MRT Kajang Line station in Greater Kuala Lumpur is, using OpenStreetMap network circuity, WorldPop population and station ridership.

![Circuity by station](outputs/figures/circuity_by_station.png)

## Why

A station 400m away as the crow flies can be a 3km walk if highways, rail lines or rivers block the direct route. Catchment maps usually draw straight-line circles around stations, which hides these barriers. This project measures the actual walking route from each residential area to its station and flags stations where residents face long detours.

## Approach

1. **Stations:** coordinates for the 29 Kajang Line stations from GTFS static feeds.
2. **Residential areas:** residential land use within each station's 800m catchment, extracted from OpenStreetMap.
3. **Circuity:** for every residential area, the walking-network distance to the station divided by the straight-line distance. A circuity of 2 means the walk is twice the direct distance.
4. **Population:** residents in each 800m catchment, summed from the WorldPop raster.
5. **Ridership:** average daily boardings per station from data.gov.my origin-destination data (log-transformed, as it is right-skewed).
6. **Clustering:** k-means on standardised mean circuity, population and the log ridership gap (ridership relative to what population predicts), with k chosen so that each cluster maps to a distinct intervention type.

**Tools:** R, `sf`, `osmextract`, `sfnetworks`, `tidyverse`, `cluster`, `factoextra`, [raster package, e.g. `terra` / `exactextractr`].

## Key findings

- **Walking access varies widely along the line.** Mean station circuity ranges from 1.29 to 4.21 (line average 1.82).
- **Poorer access is associated with lower use.** Circuity and log ridership are negatively correlated (r = −0.40, p = 0.031).
- **Taman Suntex shows a clear barrier pattern.** 9 of its 23 residential areas face detours of 3.3–10.2×; one area 334m from the station is a 3.4km walk.
- **Population barely predicts ridership** (R² = 0.02). [n] stations record more daily boardings than they have catchment residents, so heavy use at central and interchange stations comes mainly from non-residents.
- **Clusters:** [k] groups — [one line per cluster: profile, example stations, suggested intervention].

![Clusters](outputs/figures/clusters.png)

## Limitations

- 29 stations is a small sample, and cluster structure is weak (silhouette 0.25–0.32), so clusters are best read as a screening step for site-level assessment.
- OpenStreetMap footpaths are incomplete; missing crossings or footbridges can inflate circuity. Network gaps were resolved by node snapping, which produced five area-level values below 1 at very short distances.
- Bukit Dukung's circuity rests on only 3 routable residential areas and is treated as low-reliability.
- Circuity is averaged across residential areas without population weighting.
- Ridership measures realised demand, not people deterred from using the station.

## Reproducing the analysis

1. Download the raw data into `data/raw/` (see Data sources below).
2. Restore package versions:
   ```r
   install.packages("renv")
   renv::restore()
   ```
3. Run `analysis.Rmd`.

The network build takes about 90 minutes on a laptop. To skip it, the processed outputs in `data/processed/` (`all_summary.rds`, `all_detail.rds`) let you run the ridership and clustering sections directly.

## Repository structure

```
├── analysis.Rmd          # main analysis
├── R/                    # helper functions
├── data/
│   ├── raw/              # not tracked; download separately
│   └── processed/        # station- and area-level circuity outputs
└── outputs/figures/      # figures used in this README
```

## Data sources

| Data | Source |
|---|---|
| Station locations (GTFS static) | [data.gov.my GTFS static](https://developer.data.gov.my/realtime-api/gtfs-static) |
| Station ridership (origin-destination) | [data.gov.my — link to dataset] |
| Pedestrian network and residential land use | [OpenStreetMap via Geofabrik](https://download.geofabrik.de/asia/malaysia-singapore-brunei.html) |
| Population | [WorldPop](https://hub.worldpop.org/) — [dataset name and year] |

OpenStreetMap data © OpenStreetMap contributors, available under the Open Database License.
