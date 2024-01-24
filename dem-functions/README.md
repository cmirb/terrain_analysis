# Installing GDAL in a Conda Environment for VS Code

## Introduction
This guide provides a step-by-step guide to installing GDAL in a Conda environment for use in VS Code. This guide is intended for Windows users.

## Prerequisites
- [Anaconda](https://www.anaconda.com/products/individual) installed
- [Visual Studio Code](https://code.visualstudio.com/) installed
- [VS Code Python Extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) installed
- [VS Code Jupyter Extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) installed

## Steps
1. Open Anaconda Prompt
2. Create a new Conda environment
    ```
    conda create -n gdal_env python=3.11
    ```
3. Activate the new Conda environment
    ```conda activate gdal_env```
4. Install GDAL
    In your browser, go to https://www.lfd.uci.edu/~gohlke/pythonlibs/#gdal and download the appropriate GDAL wheel file for your system. For example, if you are using Python 3.11 on a 64-bit system, download `GDAL‑3.3.2‑cp311‑cp311‑win_amd64.whl`.
    ```
5. Go to your downloads folder
    ```
    cd Downloads
    ```
6. Install GDAL (using the file name from step 4, which you can just ctrl+v into the command)
    ```python -m pip install GDAL‑3.3.2‑cp311‑cp311‑win_amd64.whl``` 
7. Check GDAL installation
    ```python -m pip show gdal```
    ```
8. Import gdal in anacoda prompt
    ```python
    >>> from osgeo import gdal
    >>> from osgeo import ogr
    >>> from osgeo import osr
    >>> quit()
    ```
9. Install other packages
    ```cd ..``` (to go back to the base directory)
    ```conda install numpy```
    ```conda install pandas```
    ```conda install matplotlib```
    ```conda install seaborn```
    ```conda install -c conda-forge geopandas```
10. Go to VS code and open new file
    ```Ctrl+Shift+P```
    ```Python: Create New Blank Jupyter Notebook```
11. Select the new conda environment (you need to select the gdal_env that you created)
    ```Ctrl+Shift+P```
    ```Python: Select Interpreter```
    ```gdal_env```

## Trouble Shooting
### GDAL installation fails
- ensure that the downloaded GDAL wheel file is in your downloads folder and matches your python version and system architecture
- verify that you have necessary permissions to install packages
### Environment not showing up in VS Code
- ensure that you have the VS Code Python Extension installed
- restart VS Code after setting up the Conda environment to refresh interpreter list
- if env still doesn't show up, try manually entering the path to the python exe in the gdal env  

## Conclusion
You should now have a working GDAL environment in VS Code. You can now use GDAL in VS Code to read and write raster and vector data.