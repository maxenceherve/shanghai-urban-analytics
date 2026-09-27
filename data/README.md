# Data

Raw data is not versioned in this repository (file sizes range from ~30MB to ~2.6GB, and licensing for the purchased datasets is unclear). To rerun the notebooks, place the following files in this `data/` folder (or update the paths at the top of each notebook).

| File | Used by | Rows | Description | Source |
|---|---|---|---|---|
| `utseus-anjuke-real-estate.pk` | `01`, `02` | 467,029 listings | Shanghai housing listings (address, price, surface, district, GPS...), scraped for UTSEUS in 2017. Stored as a pickled list of lists (first row = column names). | [Anjuke](https://shanghai.anjuke.com/sale) |
| `shanghaiPOI2017.csv` | `01`, `02` | 1,048,575 POIs | Points of interest for Shanghai, classified by a Chinese national POI taxonomy (`GBCODE`, per GB/T 35648-2017). Bought from Gaode (AMap) for the SHU Cendus institute in 2020; the 2017 vintage was selected to match the Anjuke listings year. | Gaode / AMap (purchased dataset) |
| `上海市-POI.shp` (+ `.dbf`, `.shx`, `.prj`, `.cpg`) | `03` | 1,754,933 POIs | A separate, more recent POI export (timestamps from 2024) used only for the walkability analysis, with AMap-style fields (`bigType`/`midType`/`smallType`/`typecode`). **Source not documented** in the original project files — the field structure suggests an AMap/Gaode POI export, but this was not confirmed. | Not documented |
| `sh-villages.geojson` | `03` | 5,614 polygons | Community/village-level administrative boundaries for Shanghai (`ad_code`, `name`), used as the walkability analysis's spatial units. **Source not documented** in the original project files. | Not documented |

## Rebuilding

1. Obtain each file above from its source (or from whoever originally distributed them for the UTSEUS course) and place it directly in this `data/` folder.
2. The notebooks read these files by their exact names shown above, from the working directory — no further preprocessing is required before running them top to bottom.
