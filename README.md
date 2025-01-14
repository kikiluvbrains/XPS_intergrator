# XPS_intergrator 

The XPS intergrator executable for windows is still under development, for the LAND data plotting tool is free to use.

![Screenshot from 2024-11-17 18-35-04](https://github.com/user-attachments/assets/0e2e49c2-abbe-4eef-99f9-cb8ba9112040)

    1. Select load data you can click and select multiple files to plot multiple Land data
    2. Adjust Plot title, and Marker size and all other fields as needed
    3. Click on “Plot Data”
    4. Select “Save Plot” to save it as a .png or .jpg file

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
![image](https://github.com/user-attachments/assets/4ce8c66d-dbda-469d-a8ca-0001537f0d30)

## License
This project is licensed under the MIT License.
