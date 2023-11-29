# Solar
The [data](https://drive.google.com/drive/folders/1ZfTCTzwVR_ocT4d2z7GFagyXZpgfqjZ8) we made during preprocessing.
## Demo is [DSCOVR_pdf](https://github.com/MohdJunaiduddin/Solar/blob/main/Purple%20Modern%20Space%20Presentation.pdf).
## Problem Statement
- The Deep Space Climate Observatory (DSCOVR), can measure the strength and speed of the solar wind in space, which enables us to predict geomagnetic storms that can severely impact important systems like GPS and electrical power grids on Earth. DSCOVR, however, continues to operate past its expected lifetime and produces occasional faults that may themselves be indicators of space weather. Our challenge is to use the "raw" data from DSCOVR—faults and all—to predict geomagnetic storms on Earth.
## Idea
- We took a variety of international data sources (such as NASA, NOAA magnetic observatory in Japan and German Research Centre for Geosciences) as dataset for the model we used, to predict geomagnetic storms. we actually derived the storms binary classification (i.e., true/false) column from kpa values(if kpa>5.5 geostorm: true else kpa<5.5 geostorm:false).
## Data
- The Link [data](https://www.spaceappschallenge.org/develop-the-oracle-of-dscovr-experimental-data-repository/) has datasets:
DSCOVR PlasMAG yyyy data consists of human-readable text format ,with one 1-min measurement set per line.
