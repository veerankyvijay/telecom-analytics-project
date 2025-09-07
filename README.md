# telecom-analytics-project

This is a detailed analysis of the mobile phone dataset, suitable for a GitHub README.md file.

```markdown
# Telecommunication Industry Project: Mobile Phone Data Analysis

## Introduction

This project is part of my learning experience in applied statistics and focuses on analyzing a dataset containing mobile phone prices and their specifications. The goal is to understand the characteristics of the phones in the dataset and apply logical conditions to filter the data based on specific criteria.

## Dataset Columns Information

The dataset includes the following columns:

*   **PID**: A unique identifier for each phone model.
*   **Blue**: Indicates whether the phone has Bluetooth support (`yes`/`no`).
*   **Wi_Fi**: Indicates whether the phone has Wi-Fi support (`yes`/`no`).
*   **Tch_Scr**: Indicates whether the phone has touchscreen support (`yes`/`no`).
*   **Ext_Mem**: Indicates whether the phone has external memory support (`yes`/`no`).
*   **Px_h**: Number of pixels in the vertical axis of the phone screen.
*   **Px_w**: Number of pixels in the horizontal axis of the phone screen.
*   **Scr_h**: Height of the phone screen in centimeters (cm).
*   **Scr_w**: Width of the phone screen in centimeters (cm).
*   **Int_Mem**: Internal memory of the phone in megabytes (MB).
*   **Bty_Pwr**: Maximum energy stored by the phone's battery in milli-Ampere-hours (mAh).
*   **PC**: Resolution of the primary camera in megapixels (MP).
*   **FC**: Resolution of the front camera in megapixels (MP).
*   **RAM**: Random Access Memory available in the phone in gigabytes (GB).
*   **Depth**: Depth of the mobile phone in centimeters (cm).
*   **Weight**: Weight of the mobile phone in grams (g).
*   **Price**: Selling price of the mobile phone in rupees.

## Analysis Overview

The analysis proceeds through several tasks, focusing on data loading, initial exploration, and applying logical conditions to filter phones based on desired features.

### Task 1: Loading and Studying the Data

**Libraries Used:**
*   `numpy` for numerical operations.
*   `pandas` for data manipulation and analysis.
*   `matplotlib.pyplot` for data visualization.
*   `seaborn` for enhanced data visualization.

**Data Loading and Initial Inspection:**
The `telecom.csv` file was loaded into a pandas DataFrame.
*   `data.head()` was used to display the first few rows of the dataset, providing a quick overview of the data structure and values.
*   `data.ndim` confirmed that the dataset is a 2-dimensional DataFrame.
*   `data.shape` revealed that the dataset contains 50 rows (phones) and 17 columns (features).
*   `data.columns` listed all column names.
*   `data.info()` provided a summary of the DataFrame, including data types and non-null counts for each column.

**Observations from Task 1:**
*   The dataset contains 50 mobile phone entries.
*   There are 17 features, including `PID` which serves as a unique identifier.
*   Crucially, there are no missing values in the dataset, which simplifies the subsequent analysis steps.

### Task 2: Logical Conditions for Binary Features (`Blue`, `Wi_Fi`, `Tch_Scr`, `Ext_Mem`)

This task focused on filtering phones based on common binary features. The objective was to identify phones that possess all four desired features: Bluetooth, Wi-Fi, touchscreen, and external memory support.

**Approach:**
*   A new logical condition, `con1`, was created.
*   This condition checks if `Blue`, `Wi_Fi`, `Tch_Scr`, and `Ext_Mem` columns all have a value of `yes` (assuming 'yes' is represented as 1 after potential conversion, or directly if the data is already boolean).
*   The `&` (AND) operator was used to combine these conditions, ensuring that only phones meeting all criteria are selected.
*   The `con1` column was added to the DataFrame to store the boolean results of this condition.

**Observations from Task 2:**
*   The features `Blue`, `Wi_Fi`, `Tch_Scr`, and `Ext_Mem` are binary in nature.
*   The logical condition `con1` successfully captures phones that satisfy all these desired features, reflecting the children's preferences.

### Task 3: Logical Conditions for Screen Resolution (`Px_h`, `Px_w`)

This task aimed to identify phones with good screen resolutions.

**Approach:**
*   A new feature, `Px`, was created by multiplying `Px_h` (vertical pixels) and `Px_w` (horizontal pixels) to represent the total screen resolution.
*   A histogram of the `Px` feature was plotted, along with vertical lines indicating the mean and median values, to visualize the distribution of screen resolutions.
*   The median value of `Px` was calculated.
*   A logical condition, `con2`, was created to select phones with a `Px` value greater than or equal to the median `Px`.
*   The `con2` column was added to the DataFrame.

**Observations from Task 3:**
*   The `Px_h` and `Px_w` features represent the pixel dimensions of the phone screen.
*   The `Px` feature provides a comprehensive measure of screen resolution.
*   The median was chosen as the threshold for "good" screen resolution. This choice can be adjusted to the mean if a less strict criterion is desired.

### Task 4: Logical Conditions for Screen Size (`Scr_h`, `Scr_w`)

This task focused on identifying phones with desirable screen sizes.

**Approach:**
*   A new feature, `Scr_d`, was created to represent the length of the screen diagonal using the Pythagorean theorem (`sqrt(Scr_h^2 + Scr_w^2)`).
*   A histogram of the `Scr_d` feature was plotted, showing the quartiles (Q1, Median, Q3) to understand the distribution of screen diagonal lengths.
*   The upper quartile (Q3) of the `Scr` feature (calculated as `Scr_h * Scr_w`) was determined.
*   A logical condition, `con3`, was created to select phones with a `Scr` value greater than or equal to the upper quartile.
*   The `con3` column was added to the DataFrame.

**Observations from Task 4:**
*   `Scr_h` and `Scr_w` represent the physical dimensions of the screen.
*   `Scr_d` provides a useful metric for screen diagonal.
*   The upper quartile was chosen as a strict threshold for "very good" screen size, aligning with specific preferences. This threshold can be relaxed to the mean or median if needed.

### Task 5: Logical Conditions for Camera Resolutions (`PC`, `FC`)

This task aimed to filter phones based on their camera capabilities.

**Approach:**
*   Histograms for both `PC` (primary camera) and `FC` (front camera) features were plotted, showing their respective mean and median values.
*   The mean values for `PC` and `FC` were calculated.
*   A logical condition, `con4`, was created to select phones where both `PC` and `FC` resolutions are greater than or equal to their respective mean values.
*   The `con4` column was added to the DataFrame.

**Observations from Task 5:**
*   `PC` and `FC` represent the resolutions of the primary and front cameras.
*   The mean was chosen as the threshold for "good" camera resolution. Similar to previous tasks, medians could be used for a stricter criterion.

### Task 6: Logical Conditions for Performance Features (`Int_Mem`, `Bty_Pwr`, `RAM`)

This task focused on identifying phones with strong performance specifications.

**Approach:**
*   Histograms for `Int_Mem` (internal memory), `Bty_Pwr` (battery power), and `RAM` (Random Access Memory) were plotted, showing their respective mean and median values.
*   The mean values for `Int_Mem`, `Bty_Pwr`, and `RAM` were calculated.
*   A logical condition, `con5`, was created to select phones where `Int_Mem`, `Bty_Pwr`, and `RAM` are all greater than or equal to their respective mean values.
*   The `con5` column was added to the DataFrame.

**Observations from Task 6:**
*   `Int_Mem`, `Bty_Pwr`, and `RAM` are key indicators of phone performance.
*   The mean was used as the threshold for "good" performance features. Medians could be considered for a more stringent selection.

### Task 7: Logical Conditions for Physical Attributes (`Depth`, `Weight`)

This task aimed to filter phones based on their physical dimensions, specifically depth and weight.

**Approach:**
*   Histograms for `Depth` and `Weight` were plotted, showing their respective mean and median values.
*   The mean values for `Depth` and `Weight` were calculated.
*   A logical condition, `con6`, was created to select phones where `Depth` and `Weight` are less than or equal to their respective mean values (assuming a preference for thinner and lighter phones).
*   The `con6` column was added to the DataFrame.

**Observations from Task 7:**
*   `Depth` and `Weight` describe the physical characteristics of the phones.
*   The mean was chosen as the threshold, with the condition set to "less than or equal to" to favor more compact and lighter devices.

## Conclusion

This project successfully demonstrates how to load, explore, and apply various logical conditions to a mobile phone dataset using Python's pandas, numpy, matplotlib, and seaborn libraries. By creating new features and applying statistical measures like mean, median, and quartiles, the dataset can be effectively filtered to identify phones that meet specific user preferences across a range of specifications. The generated boolean columns (`con1` through `con6`) provide a flexible way to combine these criteria for more complex filtering scenarios.
```
