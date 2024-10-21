# PROSAIL-Biomass-Model

## Above Ground Biomass Estimation Using PROSAIL
This repository contains a Python notebook that implements the PROSAIL model to estimate above-ground biomass (AGB) using PlanetScope 8-band imagery. The approach combines remote sensing reflectance data with simulation techniques to derive key vegetation parameters.

## Table of Contents
  - Introduction
  - Methodology
  - Requirements
  - Usage
  - Results
  - License

### Introduction
Estimating above-ground biomass (AGB) is crucial for understanding ecosystem health and carbon cycling. This project utilizes the PROSAIL model, which combines the PROSPECT leaf optical properties model and the SAIL canopy reflectance model, to simulate reflectance based on various leaf and canopy parameters.

### Methodology
  - Data Acquisition:
    The project uses PlanetScope 8-band imagery. The bands are associated with specific wavelengths critical for vegetation analysis.
  - PROSAIL Simulation:
    The reflectance for various combinations of Leaf Area Index (LAI) and Dry Matter Content (DMC) is simulated using the PROSAIL model.
    A Look-Up Table (LUT) is created, storing the spectral reflectance values corresponding to different LAI and DMC combinations.
  - Reflectance Comparison:
    Observed reflectance data from the PlanetScope imagery is compared to the LUT using Root Mean Square Error (RMSE) to find the best-fit LAI and DMC for each pixel.
  - AGB Calculation:
    The AGB is calculated using the best-fit LAI and DMC values. The formula used is:
      AGB = LAI × DMC

### Output:
The AGB values are saved as a GeoTIFF file for further analysis and visualization.

### Requirements
This project requires the following Python packages:
  - numpy
  - rasterio
  - scipy
  - pyprosail
  - 
  You can install the required packages using pip:
  bash
  pip install numpy rasterio scipy pyprosail

### Usage
Clone the repository:
bash
git clone https://github.com/yourusername/repository-name.git


### Results
The output of the model will be a GeoTIFF file named biomass_raster.tif, which contains the estimated above-ground biomass for each pixel in the input imagery.
