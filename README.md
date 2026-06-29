# HDF5 Gaussian Signal Analyzer

A Python-based graphical application for detecting and analyzing signals in HDF5 datasets using Gaussian fitting. The software provides an interactive GUI for browsing HDF5 files, selecting datasets, detecting peaks using configurable threshold values, fitting Gaussian profiles to detected signals, and generating summary reports.

---

## Features

* Interactive graphical user interface (GUI).
* Load and browse HDF5 (`.h5` / `.hdf5`) files.
* View the internal structure of HDF5 datasets before analysis.
* Select custom row and column ranges for analysis.
* Detect signals using Gaussian fitting.
* Supports **two independent threshold regions**:

  * Global threshold applied across the entire dataset.
  * Central-region threshold applied to a user-defined section.
* Configurable threshold multipliers using interactive sliders.
* Automatic Gaussian fitting for each detected signal.
* Peak lockout mechanism to prevent duplicate detections of nearby signals. By default, signals occurring within a predefined point range after a detected peak are ignored to reduce multiple detections of the same event.
* Live visualization of waveforms, thresholds, and Gaussian fits.
* Continuous processing of multiple traces.
* Automatic generation of a Microsoft Word summary report.
* Individual peak information is saved for every detected signal.

---

## Supported File Format

Currently supports only:

* `.h5`
* `.hdf5`

---

## Detection Method

The software calculates the baseline mean and standard deviation of the selected dataset. Signal detection is performed using configurable threshold values based on

**Threshold = Mean − n × Standard Deviation**

where the multiplier **n** can be adjusted independently for both the global region and the central region.

Whenever a signal is detected, the program performs a Gaussian fit to determine the peak position and fitting parameters.

To avoid counting the same event multiple times, the software ignores additional detections occurring within a predefined lockout distance after a detected peak. The lockout distance, threshold values, fitting parameters, and other analysis settings can all be modified directly in the Python source code.

---

## Outputs

The software generates:

* Interactive waveform plots
* Gaussian fit overlays
* Peak parameter text files
* Microsoft Word summary report containing peak statistics
* Peak count for each processed trace

---

## Requirements

* Python 3.x
* NumPy
* SciPy
* Matplotlib
* h5py
* python-docx
* Tkinter

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

## Running the Program

```bash
python main.py
```

or download the standalone Windows executable from the **Releases** section of this repository.

---

## Future Improvements

* Batch processing of multiple HDF5 files together.
* CSV and Excel export options.
* Improved visualization tools.

---

## Citation Request

If this software contributes to your research, publications, or academic work, please consider citing this repository or acknowledging its use in your manuscript. Proper citation helps support the continued development and maintenance of this project.

---

## Author

**Rahul Das**

Integrated BS-MS (Physics)

Indian Institute of Science Education and Research (IISER) Tirupati
