# Traffic Signal Timing Optimization for Urban Intersections

## ESE 5971 — Milestone 2
Student: Yanjun Ke

## 1. Project Objective

This project aims to support traffic signal timing decisions
at urban intersections.

The long-term goal is to reduce traffic delay and improve
intersection performance.

For Milestone 2, the focus is on understanding the
data-generating process, data quality, temporal dependence,
and preliminary analytical design.

The current prediction task estimates future detector occupancy.
It does not directly optimize signal timing.

## 2. Dataset

Data source: ETH Zurich Traffic Signal Control Dataset

Dataset:
https://www.research-collection.ethz.ch/handle/20.500.11850/556642

The dataset contains real observations from one signalized
urban intersection in Zurich, Switzerland.

Period: January 1 to February 28, 2019

Total records: 5,076,422

Variables:
- time: timestamp
- d1–d10: loop detector occupancy states
- sg1–sg12: traffic signal group states

The original observations have one-second resolution.

## 3. Repository Structure

traffic-signal-m2/
- README.md
- requirements.txt
- .gitignore
- data/
  - README.md
  - raw/
- notebooks/
  - milestone2_analysis.ipynb
- figures/

## 4. Setup and Execution

1. Download the dataset ZIP from the source.
2. Place Traffic_Signal_Control_Dataset.zip in data/raw/.
3. Install dependencies:

   python -m pip install -r requirements.txt

4. Open notebooks/milestone2_analysis.ipynb in Jupyter or VS Code.
5. Restart the kernel and run all cells.

The notebook reads CSV files directly from the ZIP archive.

## 5. Analysis

The notebook includes:

- Data loading and timestamp validation
- Missingness and data quality checks
- Signal code investigation
- Five-minute detector occupancy aggregation
- Exploratory data analysis
- High-occupancy anomaly investigation
- Temporal autocorrelation analysis
- Chronological training, validation, and test splitting
- Baseline prediction and evaluation

## 6. Preliminary Validation

The prediction target is d5 occupancy in the next
five-minute interval.

Training: January 1–31, 2019
Validation: February 1–15, 2019
Test: February 16–28, 2019

Two baselines were evaluated on the validation set:

- Persistence MAE: 0.031815
- Time-of-Day MAE: 0.030615

MAE is measured in occupancy fraction.

## 7. Limitations

The dataset does not directly provide vehicle delay
or queue length.

Signal code 8 requires further documentation.

Temporal dependence makes random row-level splitting
inappropriate.

The available observations do not establish causal effects
of alternative signal timing plans.

## 8. Reproducibility

The notebook was checked using Restart Kernel and Run All.

All reproducibility checks passed.

The original dataset is not included in this repository
because it is a large external dataset.

The dataset must be downloaded separately.