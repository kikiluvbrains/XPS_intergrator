# XPS_intergrator

!pip install numpy matplotlib pandas

## Description

This method requires you to specify **two compounds**, along with their respective **scaling factors** for it to run. You can also set the scaling factor to `"None"` if you do not wish to apply a scaling factor.

The process involves calculating the **AUC (Area Under the Curve)** using the **trapezoidal method**. First, the total AUC is computed, and the AUC below the baseline is subtracted, leaving only the AUC for the peaks. The **baseline-corrected AUC** is then divided by the scaling factor from the ASF table.

Next, the baseline-corrected and scaled AUC for **Compound A** and **Compound B** are obtained, and the ratio is determined by dividing **A** by **B**.

!!!Disclaimer: The code is currently made to run on Jupiter Notebook
---

## Usage Instructions

To run this analysis, you must specify **two compounds** along with their respective **scaling factors**. If you do not wish to apply a scaling factor, set the value to `"None"`.

The AUC (Area Under the Curve) is calculated using the **trapezoidal method**. Here's how the process works:

1. The **total AUC** is computed.
2. The **AUC below the baseline** is subtracted, leaving only the **AUC for the peaks**.
3. The **baseline-corrected AUC** is divided by the **scaling factor** provided from the ASF table.

Once the baseline-corrected and scaled AUCs for **Compound A** and **Compound B** are obtained, the ratio is calculated by dividing **A** by **B**.

This process will be documented for reference.

---

## Example Code Block



## Example Usage

```python
# Example usage:
file_path_A = '/home/location/Downloads/sample Sr3d.xlsx'
file_path_B = '/home/location/Downloads/sample Ti2p.xlsx'
plot_title = 'Area Under the Sorted Curve: Sr3d vs Ti2p'
x_label = 'Binding'
y_label = 'Counts'
name_compound_A = 'Sr3d'
name_compound_B = 'Ti2p'
scaling_factor_A = 1.578  # Scaling factor for compound A
scaling_factor_B = 1.798  # Scaling factor for compound B
x_A = 1  # The column number for Binding in file A
y_A = 3  # The column number for Counts in file A
x_B = 1  # The column number for Binding in file B
y_B = 3  # The column number for Counts in file B

# Optional Binding ranges: uncomment to apply constraints
binding_range_A = (130, 138)  # Optional range for Sr3d, set to None if not used
binding_range_B = (455, 466)  # Optional range for Ti2p, set to None if not used

plot_curve_from_excel(
    file_path_A, 
    file_path_B, 
    plot_title, 
    x_label, 
    y_label, 
    x_A, 
    y_A, 
    x_B, 
    y_B, 
    scaling_factor_A, 
    scaling_factor_B, 
    name_compound_A, 
    name_compound_B, 
    binding_range_A, 
    binding_range_B
)
```
## License
This project is licensed under the MIT License.
