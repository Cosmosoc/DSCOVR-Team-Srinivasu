# Solar
The [data](https://drive.google.com/drive/folders/1ZfTCTzwVR_ocT4d2z7GFagyXZpgfqjZ8) we made during preprocessing.
## Demo is [DSCOVR_pdf](https://github.com/MohdJunaiduddin/Solar/blob/main/Purple%20Modern%20Space%20Presentation.pdf).
## Problem Statement
- The Deep Space Climate Observatory (DSCOVR), can measure the strength and speed of the solar wind in space, which enables us to predict geomagnetic storms that can severely impact important systems like GPS and electrical power grids on Earth. DSCOVR, however, continues to operate past its expected lifetime and produces occasional faults that may themselves be indicators of space weather. Our challenge is to use the "raw" data from DSCOVR—faults and all—to predict geomagnetic storms on Earth.
## Idea
- We took a variety of international data sources (such as NASA, NOAA magnetic observatory in Japan and German Research Centre for Geosciences) as dataset for the model we used, to predict geomagnetic storms.
## Data
- The Link [data](https://www.spaceappschallenge.org/develop-the-oracle-of-dscovr-experimental-data-repository/) has datasets:
DSCOVR PlasMAG yyyy data consists of human-readable text format ,with one 1-min measurement set per line.
- The data file contains 54 columns -0 column -date and time, columns(1-3)->components of the magnetic field vector.columns(4-53)-ecah value corresponds to the flux in a particular range of energies.
- The 0 values in data represents NAN .We coverted 0 to NAN .
- For Kp values we took data from [kp data](https://kp.gfz-potsdam.de/en/data#c222) for solar strom prediction.
## pre-processing
- From given raw data,we took 2022 and 2021 data .
- Dataset of 2022:We dropped d29 to d49 columns with have more then 50% nan values and for x, y, z, d0 t0 d22 used KNNImputer to predict the nan values for d23 to d28 used interpolate linear method.
- Dataset of 2021:We dropped d29 to d49 columns with have more then 50% nan values
 and for x, y, z, d0 t0 d17 used KNNImputer to predict the nan values for
 d18 to d28 used interpolate linear method. We stored all data in new csv ([data](https://drive.google.com/drive/folders/1ZfTCTzwVR_ocT4d2z7GFagyXZpgfqjZ8)).
-  In,pre-processing, took the kp data from  [kp data](https://kp.gfz-potsdam.de/en/data#c222) for 2022 and 2021 this data has few missing data which are filled by interpolate liner method.
-   Added  new columns in the existing dataset named kp_val, geoStorm_01.
## Model
- After pre-processing, the final model used to predict is by LSTM. It is model designed to predict a value for Kp.
- We made multiple models by changing the number of neurons and layers.
- The best one is till now has, First LSTM layer with 25 neurons and 'relu' activation, Second LSTM layer with 15 neurons, Third LSTM layer with 10 neurons, TimeDistributed Dense layer with 1 neuron and 'relu' activation.
-Adam's optimizer was used to optimize and utilized the mse as loss function.
- 3 models have been uploded named m_numberOfNeuronsInFirstLayer_numberOfEpochs (ex m_30_150 is model obtained from using model with fisrt layer having 30 neurons and trained for 150 epochs).
