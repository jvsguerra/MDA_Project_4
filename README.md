# Project 4

This repository contains the source code for the Project 4 for the **Microscopy data analysis: machine learning and the BioImage archive** course.

## Description

The project uses programming skills acquired during the course.

The authors of the PLOS Biology paper, "Nessys: A new set of tools for the automated detection of nuclei within intact tissues and dense 3D cultures" published in August 2019: https://doi.org/10.1371/journal.pbio.3000388  (Blin et al 2019) introduced a novel nuclear segmentation method. The images were processed by Nessys, an extensible software written in Java for the automated identification of cell nuclei. The images and analytical results have been published in IDR see <https://idr.openmicroscopy.org/webclient/?show=project-801>.

The data have also been converted into OME-Zarr by the IDR team.

Cellpose was not used by the authors of the paper.

Your task is to re-analyse some of their data using Cellpose Python API (i.e. not the GUI application) and compare the output with the original segmentation produced by the authors.

For this project, we aim to analyse data in parallel using the Dask package and by “lazy” loading the data, first using a local TIFF file and then repeating the process using the corresponding ome.zarr file

For this project, you will have to:
- Step 1:
 
  - Prepare a notebook runnable in the virtual environment on the Virtual Machine. Install the relevant dependencies from https://pypi.org/
  - Using the URL, download the B4_C3.tif image from IDR 
Try to open in BioIO. If it fails, suggest how to solve the issue, (Think OME-TIFF);
  - Analyse in parallel a few planes e.g. 2 around the middle z-section of the local data using the Cellpose API and the default Cellpose ``cyto`` model. 
  - Display the result.

- Step 2:
  
  - Redo the analysis in parallel but this time reading the 6001247.zarr file;
  - Read the labels from the ome.zarr and compare them with the output of the Cellpose analysis.

