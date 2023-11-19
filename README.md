# G16-A4
A4: OpenBIM Champion - A guide on how to use our developed code

## **Prerequisites**

1. **Python Installation:** Ensure you have Python installed on your system. You can download Python from [python.org](https://www.python.org/downloads/).
2. **Microsoft Excel Installation:** Ensure you have Microsoft Excel installed on your system. You can download Microsoft Excel from [microsoft.com](https://www.microsoft.com/en-us/microsoft-365/excel).
3. **Required Python Packages:** Install the required Python packages using the following command in the Command Prompt app:

   ```bash
   pip install ifcopenshell openpyxl
   ```

## **Instructions**

1. **Folder Setup:**
   Make sure your directory is structured as shown below:

   ```bash
   + FOLDER: `Name of your directory`
     - FILE: `main.py` - The python script
     - FILE: `List_of_densities.xlsx` - The Microsoft Excel database
     + FOLDER: `Model`
       - FILE: `G16_Skylab_Model.ifc`
   
> Note: If your IFC model has a different name, you can change the *Your_name_of_the_model* in the main.py code on line 9: `modelname = "Your_name_of_the_model"`

2. **Excel Input:**
   - Prepare an Excel spreadsheet named List_of_densities.xlsx with the following columns in the 'Sheet1' tab:
     - Column A: **Material Names** - Material Names corresponding to Material Names in the IFC model.
     - Column B: **Density Values** - Density values in kg/m3 of the selected Materials.
     - Column C: **Material Process Code** - Ecoinvent Material Process Codes
     - Column D: **Unit**
   - Additionally, include 'Ecoinvent' tab with the following columns:
     - Column B: **Ecoinvent Process Codes** - Ecoinvent Material Process Codes.
     - Column N: **Ecoinvent IPCC2021** - Global warming potential in kg CO2-eq of the selected materials.

3. **Changing the output location and name:**
   - To change the output location of the Excel file, you have to change the *C:\Users\...\Model* in the main.py code on line 318: `model.write(r'C:\Users\...\Model/Name_of_your_output.ifc')`
   - You can change the name of the output, you have to change the *Name_of_your_output.ifc* in the main.py code on line 318: `model.write(r'C:\Users\...\Model/Name_of_your_output.ifc')`

4. **Run the script:**

5. **Output:**
   - The script will generate an Excel file named material_quantities.xlsx containing the environmental impact assessment results.
   - A modified version of the original IFC model, with additional environmental information, will be saved as G16_Skylab_Modified.ifc (or as *Name_of_your_output* if changed before).

6. **Troubleshooting**
   - If the script encounters any issues, it will print error messages to the console. Review these messages to identify and resolve any problems.
   - Ensure that all file paths are correct and that the required files, including the IFC model and Excel spreadsheet, are present in the specified locations.
