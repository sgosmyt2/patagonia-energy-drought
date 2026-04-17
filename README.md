# Can Compound Wind Hydro Energy Droughts in Patagonia Be Predicted from Large-Scale Climate Modes?

## Overview

Patagonia hosts Argentina's largest concentration of wind energy capacity (2+ GW along the Atlantic coast) and its most important hydroelectric system (the Limay-Neuquén-Negro cascade, 4+ GW). Both resources are sensitive to large scale climate variability; wind generation depends on the strength and position of the Southern Hemisphere westerly jet, while hydroelectric inflows depend on Andean snowmelt and precipitation. This project investigates whether large scale climate modes (the Southern Annular Mode, ENSO, and potentially the Indian Ocean Dipole) can predict compound wind hydro energy droughts. These are periods when both resources simultaneously underperform, and if so, how far in advance.

## Key Findings

*To be completed after analysis*

## Data
ERA5 Reanalysis (Copernicus Climate Data Store)   
	- Spatial domain: 38°S-47.5°S, 72°W-62°W    
 	- Temporal domain: 1979-2025   
 	- Resolution: 0.25° monthly   
 	- Processing: Area weighted average across land grid cells within bounding box   
SAM Index (British Antarctic Survey)   
	- Southern Annular Mode (Marshall)    
	- British Antarctic Survey    
	- 1957-present     
ONI (NOAA CPC)   
	- Oceanic Niño Index    
	- NOAA CPC    
	- 1950-present    
IOD/DMI    
	-  Indian Ocean Dipole Mode Index    
	-  NOAA PSL / BOM    
	- 1870–present   
	
The SAM (Marshall station based index) is used rather than an ERA5 derived SAM to maintain independence between predictor and predictand datasets. The ONI is provided as a 3 month running mean. IOD inclusion is pending literature review.

## Methodology

### Compound Drought Index

Wind speed and runoff are standardised independently by calendar month to remove seasonal cycles, then averaged into a compound Wind Hydro Drought Index (WHDI). Equal weighting is used to avoid introducing infrastructure capacity assumptions into a climate analysis. Drought events are catalogued when WHDI3 drops below  -1.0 (moderate),  -1.5 (severe), or  -2.0 (extreme), following standardised conventions.

### Teleconnection Analysis

Lag correlation analysis quantifies the relationship between each climate mode (SAM, ONI, IOD) and the WHDI at lead times of 0-12 months. Significance is tested using effective degrees of freedom to account for autocorrelation. Composite analysis maps the spatial pattern of wind and runoff anomalies during positive vs negative phases of each climate mode. All analyses are stratified by season to capture the known seasonal dependence of Southern Hemisphere teleconnections.

### Machine Learning Forecasting

Four modelling paradigms are compared to determine which is most appropriate for climate teleconnection prediction:

## Notebooks
1. Data Collection
2. Climatology & Index Construction
3. Teleconnection Analysis
4. ML Forecasting & Anomaly Detection
5. Synthesis & Visualization

## Setup
```bash
conda env create  -f environment.yml
conda activate patagonia-energy
