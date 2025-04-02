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

Step 1: Local TIFF Image Analysis

- Set up a virtual environment and install dependencies from [PyPI](https://pypi.org/).
- Download the B4_C3.tif image from IDR.
- Attempt to open it using BioIO. If it fails, investigate and suggest solutions (e.g., OME-TIFF handling).
- Select two Z-planes around the middle of the stack.
- Process the selected planes using Cellpose API with the default cyto model.
- Display the segmentation results.

Step 2: OME-Zarr Image Analysis

- Repeat the analysis using the 6001247.zarr file instead of TIFF.
- Load segmentation labels from OME-Zarr.
- Compare the original segmentation labels (from ome.zarr) with the Cellpose output.
