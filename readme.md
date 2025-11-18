# Chicago Community Areas Amenity and Opportunity Analysis

This project analyzes amenity supply, demographic structure, and investment potential across the 77 Chicago Community Areas. The goal is to identify which neighborhoods are saturated with amenities and which are underserved, and to produce evidence based maps and rankings for potential development.

The analysis includes food, nightlife, retail, schools, gyms, and a combined opportunity index. Spatial and similarity networks are also built to study neighborhood relations and service patterns.

## Project Structure

### 01_data_pipeline.ipynb
Builds the base amenity dataset using:
- Business Licenses
- Food Inspections
- Liquor Licenses
- Building Permits

Each dataset is cleaned, geocoded, and spatially joined to Community Areas. Counts are aggregated per CA.

### 02_demographics.ipynb
Merges demographic indicators from Community Area profiles:
- percent dependents
- percent working age
- per capita income
- hardship index

This file creates a combined demographic and amenity dataset for further analysis.

### 03_saturation_index.ipynb
Creates an amenity saturation index based on scaled counts of:
- business licenses
- food inspections
- liquor licenses
- building permits

The result identifies the most saturated and least saturated areas for nightlife and food related activities.

### 04_networks.ipynb
Builds two neighborhood networks:
- Spatial adjacency network using polygon boundaries
- Similarity network using amenity and demographic profiles

Computes centrality measures and saves network structures. These networks reveal clusters and structural relations across Community Areas.

### 05_visualizations.ipynb
Generates visual outputs:
- choropleth map of the saturation index
- scatter plots comparing saturation with hardship and income
- visual layouts of adjacency and similarity networks

### 07_shops_pipeline.ipynb
Processes retail related business licenses:
- Limited Business License
- Retail Food Establishment
- Tobacco Dealer
- Commercial Retail Sales
Aggregates shop and supermarket presence per Community Area.

### 08_schools_pipeline.ipynb
Processes Chicago Public Schools location data. Counts schools per Community Area to measure educational infrastructure.

### 09_combined_opportunity_index.ipynb
Creates undersupply measures for:
- bars
- gyms
- shops
- schools

Builds a combined opportunity index that identifies neighborhoods with the highest multi sector investment potential. Generates maps of opportunity zones.

### 10_sector_opportunity_maps.ipynb
Produces sector specific opportunity maps for:
- schools
- supermarkets and retail

Highlights neighborhoods with educational or commercial retail gaps.

### 11_final_opportunity_ranking.ipynb
Creates a final ranking table combining all undersupply sectors:
- bars undersupply
- gyms undersupply
- shops undersupply
- schools undersupply
- combined opportunity index

Exports a final csv with overall investment priority rankings.

### 12_visual_priority_plots.ipynb
Creates summary plots:
- bar chart of the top 10 investment opportunity areas
- heatmap of sector deficits across all Community Areas

## Data Sources

Chicago Data Portal:
- Business Licenses  
- Food Inspections  
- Liquor Licenses  
- Building Permits  
- Community Area Boundaries  
- Public School Locations  
- Retail filters derived from license categories  

All data is spatially joined to official Community Area polygons.

## Key Outputs

- saturation_index_by_CA.csv  
- retail_by_CA.csv  
- schools_by_CA.csv  
- combined_opportunity_index_by_CA.csv  
- final_opportunity_ranking.csv  
- adjacency and similarity network graphs  
- sector specific and combined opportunity maps  
- top ten investment opportunity plots  
- heatmap of undersupply patterns  

## Interpretation

The analysis identifies Chicago neighborhoods that have:
- high amenity saturation  
- low amenity availability  
- gaps in nightlife, fitness, retail, and schools  
- strong multi sector investment potential  

Consistent patterns show high undersupply in several South Side, Southwest Side, and Far West Side neighborhoods. North Side and downtown areas generally show high saturation and low opportunity levels.

## How to Use This Project

1. Run notebooks in numerical order.
2. Use the combined opportunity index and final ranking for reporting or planning decisions.
3. Use the maps and heatmaps to interpret spatial patterns.
4. Use the networks to explore neighborhood similarity and structural relations.

This project builds a complete pipeline from raw datasets to final interpretation. It supports data driven understanding of neighborhood amenity landscapes in Chicago.
