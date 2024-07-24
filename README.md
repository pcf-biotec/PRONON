---

# PRONON - Automation Strategies for HTS Methods
---

# Heatmap Analysis Project

## Description

This project performs analysis and visualization of data from multiple Excel files. The goal is to process data, calculate means and standard deviations, and generate customized heatmaps. The resulting files are exported to specific directories to facilitate analysis and visualization.

## Features

- **Excel File Reading and Processing:** Processes multiple files and sheets, calculates basic statistics (means and standard deviations).
- **Heatmap Generation:** Creates heatmaps using customized color palettes and scaling methods.
- **Results Export:** Exports processed results and heatmaps to specific directories.

## Project Structure

- `patients/`: Folder containing the Excel files to be processed.
- `results/`: Folder where the results will be exported.
  - `results_heatmaps/`: Subfolder within `results/` where heatmaps will be saved.
- `COMPOUNDS.txt`: Text file containing compounds used in heatmap analysis.

## Dependencies

This project requires the following R packages:

- `dplyr`
- `openxlsx`
- `readxl`
- `pheatmap`
- `RColorBrewer`
- `viridis`

Install the dependencies using:

```r
install.packages(c("dplyr", "openxlsx", "readxl", "pheatmap", "RColorBrewer", "viridis"))
```

## Scripts

### `heatmap_analysis.R`

The main script performs the following operations:

1. **Import Required Libraries**
2. **Define Functions:**
   - **`split_and_process(df, cols1, cols2)`**: Splits the dataframe into two based on provided columns and calculates means and standard deviations.
   - **`read_all_sheets(file_path, cols1, cols2)`**: Reads all sheets from an Excel file and processes the data.
   - **`read_all_files(folder_path, cols1, cols2)`**: Reads all Excel files in the `patients` folder.
   - **`export_results(results, export_path, base_filename)`**: Exports calculated results to Excel files.
   - **`export_combined_results(all_sheets, export_path)`**: Creates a combined Excel file for each file in the `patients` folder.
   - **`create_heatmap_data_for_file(file_name, all_sheets, compounds)`**: Creates a combined dataframe for heatmap generation.
   - **`plot_and_export_heatmap(heatmap_data, file_name, plot_type)`**: Generates and exports heatmaps based on provided data.

3. **Script Execution:**
   - Processes Excel files in the `patients` folder.
   - Calculates means and standard deviations.
   - Exports results to Excel files.
   - Generates and exports heatmaps.

## How to Use

1. **Prepare the Environment:**
   - Install R and the necessary libraries.
   - Place the Excel files you want to process in the `patients/` folder.
   - Create the `COMPOUNDS.txt` file with the list of compounds.

2. **Run the Script:**
   - Open R or RStudio.
   - Execute the `heatmap_analysis.R` script in your environment.

3. **Results:**
   - Resulting files will be saved in the `results/` folder:
     - `*_mean.xlsx`: Contains the calculated means.
     - `*_sd.xlsx`: Contains the calculated standard deviations.
   - Heatmaps will be saved in the `results/results_heatmaps/` subfolder.

## Example

Here is an example of running the script:

```r
source("heatmap_analysis.R")
```

Be sure to adjust the file and folder paths as necessary.
