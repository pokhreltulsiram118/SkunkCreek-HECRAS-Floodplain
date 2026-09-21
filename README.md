# Skunk Creek HEC-RAS Floodplain Analysis

HEC-RAS 1D model and 100-year floodplain analysis for Skunk Creek, South Dakota, used as an independent check for SWAT+ watershed modeling.

This repository contains the HEC-RAS 1D model, supporting discharge data, terrain data, and 100-year floodplain outputs developed for Skunk Creek, South Dakota.

The HEC-RAS analysis was used as an independent hydraulic check of floodplain conditions considered in the associated SWAT+ watershed modeling study.

## Software

The model was developed and evaluated using:

- HEC-RAS 6.7 Beta 5 Development
- RAS Mapper
- 30-m terrain data

## Model Setup

The HEC-RAS project uses a steady-flow simulation representing the 100-year return-period discharge.

The main HEC-RAS project files are:

- `floodplain_analysis.prj` – HEC-RAS project file
- `floodplain_analysis.g01` – river geometry and cross sections
- `floodplain_analysis.f01` – steady-flow input
- `floodplain_analysis.p01` – simulation plan
- `floodplain_analysis.r01` – computational run file
- `floodplain_analysis.O01` – model output file
- `floodplain_analysis.g01.hdf` – geometry HDF file used by HEC-RAS and RAS Mapper
- `floodplain_analysis.p01.hdf` – computed model results used by RAS Mapper
- `floodplain_analysis.rasmap` – RAS Mapper project configuration

## Terrain Data

The `Terrain/` directory contains the terrain files used for floodplain mapping.

Files include:

- `Terrain.dem_raster_30m.tif` – 30-m terrain raster
- `Terrain.hdf` – terrain HDF file
- `Terrain.hdf.aux.xml` – auxiliary terrain metadata
- `Terrain.vrt` – virtual raster file

## Hydrologic Data

The repository also includes the discharge data used to support the 100-year return-period analysis.

- `USGS_06481500_1980_2025_daily_discharge.csv` – daily discharge record for USGS station 06481500
- `Q_return_periods_SkunkCreek.csv` – estimated return-period discharges used for the hydraulic analysis

## 100-Year Floodplain Outputs

The `1011/` directory contains the RAS Mapper outputs generated for the 100-year floodplain simulation.

Important files include:

- `Depth (100 yr).Terrain.dem_raster_30m.tif` – modeled 100-year flood depth raster
- `Depth (100 yr).vrt` – virtual raster associated with the depth output
- `1011Contour Band Polygons.shp` – floodplain contour-band polygon layer
- `1011Contour Band Polygons.dbf` – shapefile attribute table
- `1011Contour Band Polygons.shx` – shapefile index
- `1011Contour Band Polygons.prj` – coordinate reference system information

The floodplain depth raster and polygon outputs can be opened directly in QGIS or ArcGIS Pro without rerunning the HEC-RAS simulation.

## Opening the HEC-RAS Project

To open and inspect the model:

1. Download or clone this repository.
2. Open HEC-RAS.
3. Open `floodplain_analysis.prj`.
4. Open RAS Mapper.
5. Under the model results, activate the `Depth (100 yr)` layer to view the modeled 100-year floodplain.

Because the project includes the associated geometry, plan, steady-flow, terrain, HDF, and RAS Mapper files, the model configuration and previously generated results can be inspected directly.

## Purpose of the Analysis

The HEC-RAS analysis was conducted to provide an independent hydraulic check of floodplain conditions used in the associated SWAT+ watershed modeling study for Skunk Creek.

The analysis focused on the spatial extent and depth of flooding associated with the 100-year return-period discharge.

## Data Source

Streamflow data were obtained from:

**U.S. Geological Survey (USGS), Station 06481500**

Daily discharge records from 1980–2025 were used to support the return-period discharge analysis.

## Repository Structure

```text
SkunkCreek-HECRAS-Floodplain/
│
├── README.md
│
├── floodplain_analysis.prj
├── floodplain_analysis.g01
├── floodplain_analysis.f01
├── floodplain_analysis.p01
├── floodplain_analysis.r01
├── floodplain_analysis.O01
├── floodplain_analysis.g01.hdf
├── floodplain_analysis.p01.hdf
├── floodplain_analysis.rasmap
│
├── USGS_06481500_1980_2025_daily_discharge.csv
├── Q_return_periods_SkunkCreek.csv
│
├── Terrain/
│   ├── Terrain.dem_raster_30m.tif
│   ├── Terrain.hdf
│   ├── Terrain.hdf.aux.xml
│   └── Terrain.vrt
│
└── 1011/
    ├── 1011Contour Band Polygons.dbf
    ├── 1011Contour Band Polygons.prj
    ├── 1011Contour Band Polygons.shp
    ├── 1011Contour Band Polygons.shx
    ├── Depth (100 yr).Terrain.dem_raster_30m.tif
    └── Depth (100 yr).vrt
