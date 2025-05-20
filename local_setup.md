# Geospatial Python Series 1: Local Setup Guide

This guide helps you set up your environment for the Geospatial Python Series 1 workshop using Miniforge and Mamba.

## Introduction

Welcome! This workshop introduces geospatial data analysis in Python using libraries like Geopandas, Rasterio, and Xarray. By following this guide, you'll prepare your environment and datasets to work through the Jupyter Notebooks (starting with `main.ipynb`).

## Prerequisites

- **Miniforge** (includes Mamba) must be installed.
    - Download: [Miniforge GitHub](https://github.com/conda-forge/miniforge)

## 1. Download Workshop Materials

Open your terminal and run:

```bash
cd path/to/your/desired/directory
git clone https://github.com/rccgis-uchicago/geospatial_python_series1.git
cd geospatial_python_series1
```

## 2. Create the Conda Environment

Create the Conda environment using Mamba with the following command:

```bash
mamba create -n geo -c conda-forge python=3.11 gdal rasterio geopandas cartopy xarray netcdf4 h5py matplotlib pandas numpy pyproj geoviews jupyterlab
conda activate geo
```

## 3. Download Workshop Datasets

Datasets are required for the exercises. Choose one option:

- **Option A: Download all as ZIP**
    - [Download ZIP](https://uchicago.box.com/s/mrsy54p9ow78heklcf45eer10d540jb4)
    - Extract to `geospatial_python_series1/data/`

- **Option B: Download individual files**
    - Create the data directory:
        ```bash
        mkdir -p data
        ```
    - Download these files into `data/`:
        - [air.mon.mean.nc](https://uchicago.box.com/shared/static/542ixumdcsheg4dl6oxreteyieb5vezd.nc)
        - [DAYMET.004_1km_aid0001.nc](https://uchicago.box.com/shared/static/oq09g7tgnj13mzvefodcaiy5j14vig3r.nc)
        - [L08.002_CU_aid0001.nc](https://uchicago.box.com/shared/static/41mvm9b0lq1y6y2cu7t3wnxtguhgtrga.nc)
        - [MCD43A4.061_500m_aid0001.nc](https://uchicago.box.com/shared/static/14cxcvetv3l1fytpbnfwh2dl0qwp0rl9.nc)

_Notebooks expect data in `./data/`._

## 4. Run the Workshop Notebooks

With the environment active and in the project directory, launch Jupyter:

```bash
jupyter lab
# or
jupyter notebook
```

Open and run the `.ipynb` notebooks, starting with `main.ipynb`.

## Troubleshooting

- **Environment creation fails:** Check Miniforge install, `environment.yml` syntax, and network connection.
- **Command not found:** Ensure Miniforge/Conda and Git are in your PATH.
- **Update environment:**  
    ```bash
    mamba update --all -n geo
    mamba env update -n geo -f environment.yml --prune
    ```
- **Deactivate environment:**  
    ```bash
    conda deactivate
    ```
