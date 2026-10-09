# Data Documentation

## Source

ETH Zurich Traffic Signal Control Dataset

https://www.research-collection.ethz.ch/handle/20.500.11850/556642

## Original Data

The original ZIP contains four CSV files:

- intersection_data_set_jan_01_15.csv
- intersection_data_set_jan_16_31.csv
- intersection_data_set_feb_01_15.csv
- intersection_data_set_feb_16_28.csv

The data contain observations from January and February 2019.

## Data Access

Download Traffic_Signal_Control_Dataset.zip from
the original source.

Place the ZIP file in:

data/raw/Traffic_Signal_Control_Dataset.zip

The notebook reads the ZIP directly.
Manual extraction is not required.

## Variables

- time: timestamp
- d1 to d10: detector occupancy states
- sg1 to sg12: signal group states

## Known Data Quality Issues

- 21,178 missing calendar seconds
- 0 missing cell values
- 0 duplicate timestamps
- Signal code 8 appears in sg1–sg10

Code 8 is retained because its exact meaning
has not been confirmed.

## Data Processing

Detector states are aggregated into five-minute
occupancy fractions.

Incomplete time intervals are excluded from
the prediction and validation analysis.

The original data are not modified.