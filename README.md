# 2017 Thomas Fire Scar Visualization

## About
This repository contains Jupyter Notebooks for my analysis and visualization of the [2017 Thomas Fire](https://en.wikipedia.org/wiki/Thomas_Fire). This fire burned about 281,893 acres, making it the 8th largest fire in California's history. 

![thomas fire](https://ca-times.brightspotcdn.com/dims4/default/7aca077/2147483647/strip/true/crop/2048x1365+0+0/resize/1440x960!/format/webp/quality/75/?url=https%3A%2F%2Fcalifornia-times-brightspot.s3.amazonaws.com%2Fe3%2F17%2F6803239007424db677d324a459ac%2Fla-me-thomas-fire-photos-010)
Image credits: [Michael Owen Baker / For the LA Times](https://www.latimes.com/local/lanow/la-me-thomas-fire-photos-photogallery.html)

Using NASA's Landsat data and California Fire Perimeter data, I create a map that visualizes the extent of the Thomas Fire. In conjunction, I use Air Quality Index (AQI) data from the EPA to visualize the AQI surrounding the fire. Together, these visualizations showcase the impact that the Thomas Fire had on the community. 

## Repository content and structure

```
thomas-fire-analysis
├──  .gitignore
├──  README.md
└──  notebooks
     ├── aqi.ipynb
     ├── false-color.ipynb
     ├── fire-perimeter-file.ipynb
     └── thomas-fire-blog.ipynb
```

- `fire-perimeter-file.ipynb` contains the code for wrangling historic, open-source fire perimeter data to a geospatial file containing only the boundary for the 2017 Thomas Fire.
- `false-color.ipynb` contains the code for creating false color imagery from Landsat data and burn scar visualization.
- `aqi.ipynb contains the code for creating an AQI timeseries plot during the Thomas Fire from EPA's Daily AQI data.
- `thomas-fire-blog.ipynb` contains code and markdown for my [blog post about the analysis](link to blog post here).
    
## Data details

**Fire perimeters:** I use California Fire Perimeter data from the State of California's Data Catalog to create `thomas_fire_boundary.geojson`. The dataset is updated annually and includes fire perimeters dating back to 1878. 

**Landsat imagery:** I use a simplified collection of bands (red, green, blue, near-infrared and shortwave infrared) from the Landsat Collection 2 Level-2 atmosperically corrected surface reflectance data, collected by the Landsat 8 satellite. The data was retrieved from the Microsoft Planetary Computer data catalogue and pre-processed by Dr. Carmen Galaz García to remove data outside land and coarsen the spatial resolution. 



*Note:* My data folder is in the .gitignore. To run my code, access the data and add to data folder from here:
- **Fire perimeters:** Download the California_Fire_Perimeters (all) shapefile from this link: https://gis.data.cnra.ca.gov/api/download/v1/items/e3802d2abf8741a187e73a9db49d68fe/shapefile?layers=0. The code to create the boundary for the 2017 Thomas Fire from this shapefile is housed in `hwk4-task2-fire-perimeter-kochuten.ipynb`.
- **Landsat imagery:** This data is housed in the EDS 220 class server. Within the server, the data can be accessed through this path: `/courses/EDS220/data/hwk4_landsat_data landsat8-2018-01-26-sb-simplified.nc`.
 

## References

**Fire perimeters:** State of California Data Catalog (2024), *California Fire Perimeters (all)* [Data set] Available from: https://catalog.data.gov/dataset/california-fire-perimeters-all-b3436. Access date: November 18, 2024.

**Landsat imagery:** Microsoft Planetary Computer data catalogue (2024), *Landsat Collection 2 Level-2 (simplified)* [Data set] Available from: https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2. Access date: November 18, 2024.

## Acknowledgements

This repository was created as an assignment for the graduate course EDS 220: Working with Environmental Datasets in the [Masters of Environmental Data Science (MEDS) program](https://bren.ucsb.edu/masters-programs/master-environmental-data-science), taught by [Dr. Carmen Galaz García](https://github.com/carmengg).

