# Influx sort layout template program
## AKA Latin Square Generator
This program applies predefined sort templates to your BD Influx workspace.  It can also take designs from Excel and apply them to your sort.

### Installation
There are two versions here, one is an .exe that has no requirements, but is slow (as in it takes 2 seconds to start).  The other is the Python script that is fast, but requires you to install openpyxl first.  To do this use `pip install openpyxl` in Anaconda prompt or `python -m pip install openpyxl` in windows CMD.  If neither works ask the internet 'how to install Python packages'.

You need Python 3 and SortWare 1.2.0.142 (it is not tested on other versions, but probably works).

Move the script or the .exe into the SortLayout folder. E.g. “C:\Users\Public\Documents\BD\Sortware\SortLayout” and create a subfolder called 'LatSqMultiSample' 

### What are the default layouts?
The default layouts were created by Stephan Lorenz of the Sanger Institute's Single Cell Facility.  They are designed using the 'Latin Square' principle where the populations are distributed across  rows and columns to minimise batch effect.

### Multiple populations onto one plate
After completion of your normal setup and gating routine:
1. Open a 96 well or 384 well sort layout
2. Align the plate for your sort as normal
3. Assign into the first wells your gates to sort
4. Save the sort layout into the root folder of SortLayout (i.e. not a sub folder)
5. Run the script
6. Choose option ‘1’
7. Restore the sort layout.  It has the same name as the one you used to save it.
8. Proceed with your sort

### Multiple samples onto one plate
The script will produce a separate sort layout for each or your samples.  After completion of your normal setup and gating routine:
1. Create multiple overlapping gates representing the number of samples to go onto the plate 
2. Open a 96 well or 384 well sort layout
3. Align the plate for your sort as normal
4. Assign into the first wells your gates (samples) to sort
5. Save the sort layout into the root folder of SortLayout (i.e. not a sub folder)
6. Run the script
7. Choose option ‘2’
8. Restore the sort layouts from the ‘LatSqMultiSample’ subfolder.  It has created multiple layouts named after the original and appended with the name of your gate
9. Proceed with your sort and read point ‘1’ in troubleshooting

### Custom sort layouts
1. Allow the user to change the layout in the Example.xlsx file
2. Choose option 3
3. Select the example.xlsx file
4. Proceed as instructed

### Troubleshooting
The program is written in python and is commented.  Any novice python programmer should be able to help.
1.	You MUST align your plate before running the program.
2.	Do not name your sort layout or gates the same, or similar, to the sort device name, i.e. don’t use ‘384’ or ‘96’ in the layout name.
3.	The last 4 wells of the default layouts are left empty to comply with the Sanger Institutes Single Cell Facility plate format, you can change this by replacing the “” with gates.
4.	Option 2 deletes all the sort layouts in the ‘LatSqMultiSample’ subfolder before creating new ones.  So do not place anything important in there.
5.	The software does not change the number of events to be sorted.  If your template had 10 in A1 then the generated template will have 10 in A1.
