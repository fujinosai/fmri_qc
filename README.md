# fMRI Quality Control Pipeline

A comprehensive two-phase quality control pipeline for functional MRI (fMRI) data analysis. This pipeline performs automated quality assessment, threshold optimization, and data filtering to ensure high-quality fMRI data for subsequent analyses.

## Overview

This pipeline consists of two sequential phases:

- ​**Phase 1**: Threshold exploration and data precomputation
- ​**Phase 2**: Optimal threshold application and final quality control

## Features

### Phase 1: Threshold Exploration
- Comprehensive threshold space exploration
- Generation of visualization plots for threshold selection

### Phase 2: Optimal Threshold Application
- Intelligent optimal threshold selection

## Requirements

### Data Requirements
- fMRI data in MNI space (`bold_mni.nii.gz`)
- Quality control summary CSV file

## Installation

1. Download the pipeline scripts:
   - `fmri_qc_phase1.py`
   - `fmri_qc_phase2.py`


## Usage

### Phase 1: Threshold Exploration

Run the following command to start the threshold exploration phase:

```bash
python fmri_qc_phase1.py <qc_summary.csv> [--wkdir WORKING_DIR] [--config CONFIG_FILE]
```
Parameters:​​

<qc_summary.csv>: Path to the quality control summary CSV file.
[--wkdir WORKING_DIR]: Working directory path (optional, defaults to current directory).
[--config CONFIG_FILE]: Path to a custom configuration JSON file (optional).

Phase 2: Optimal Threshold Application
After completing Phase 1, run the following command to apply the optimal thresholds:

```bash
python fmri_qc_phase2.py <phase1_results_dir> <fixed_percentage> [fixed_type] [tolerance]
```
Parameters:​​

<phase1_results_dir>: Path to the directory containing Phase 1 results.
<fixed_percentage>: Target retention percentage (0-100).
[fixed_type]: Type of retention to fix (voxel or subject, defaults to voxel).
[tolerance]: Allowable tolerance around the target percentage (defaults to 1.0).
