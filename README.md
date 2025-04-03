# Project 4

This repository contains the source code for Project 4 for the "Microscopy data analysis: machine learning and the BioImage archive" course.

## Description

This project applies programming skills acquired during the course to re-analyze microscopy data using Cellpose, comparing its segmentation results with those from the Nessys algorithm.

The authors of the PLOS Biology paper, "Nessys: A new set of tools for the automated detection of nuclei within intact tissues and dense 3D cultures" (Blin et al., 2019) introduced a novel nuclear segmentation method. Their images were processed using Nessys, an extensible Java-based automated cell nuclei identification software. The images and analytical results are available in the Image Data Resource (IDR):
- <https://doi.org/10.1371/journal.pbio.3000388>
- <https://idr.openmicroscopy.org/webclient/?show=project-801>

The IDR team has also converted the dataset into OME-Zarr format. Unlike Nessys, Cellpose was not used in the original study. 

## Objective

This project aims to:
- Re-analyze the data using Cellpose (Python API, not GUI).
- Compare the results with the original Nessys segmentation.
- Optimize data handling using Dask for parallel processing and lazy loading

## Tasks

Set up a virtual environment using `uv-astral` with the following commands:

```bash
$ pip install virtualenv
$ virtualenv .venv
$ source .venv/bin/activate
```

In the virtual environment, install the required packages:

```bash
$ pip install -r requirements.txt
```

Add virtual environment to Jupyter Notebook:

```bash
$ uv python -m ipykernel install --user --name=.venv
```

Start a Jupyter Notebook server:

```bash
$ jupyter notebook Project4.ipynb
```

### Step 1: Local TIFF Image Analysis

In this step, we are going to download the B4_C3.tif file from the IDR and save it locally. Then, we will then use Cellpose to segment the nuclei in the image and compare the results with those obtained using Nessys.

The tasks are:

- Install dependencies from [PyPI](https://pypi.org/) in Jupyter Notebook;

- Download the [B4_C3.tif](https://idr.openmicroscopy.org/webclient/?show=image-6001247) image from IDR.

For more details on how to download data from IDR, access <https://idr.openmicroscopy.org/about/download.html>.

- Attempt to open it using BioIO. If it fails, investigate and suggest solutions (e.g., OME-TIFF handling).

- Select two Z-planes around the middle of the stack.

- Process the selected planes using Cellpose API with the default cyto model.

- Display the segmentation results.

### Step 2: OME-Zarr Image Analysis

In this step, we will use the OME-Zarr format to analyze the same image. We will load the image using Dask and Cellpose and compare the results with the original Nessys segmentation.

The tasks are:

- Repeat the analysis using the 6001247.zarr file instead of TIFF.

- Load segmentation labels from OME-Zarr.

- Compare the original segmentation labels (from ome.zarr) with the Cellpose output.
