# FT-ICR-MS-MS-BFS-Upper-bound-functional-group-capacity
Linking MS/MS fragmentation to molecular functionality in complex DOM systems.
Precursor Extraction from FT-ICR MS Data

This repository provides a workflow to extract precursor ions from FT-ICR MS datasets based on predefined m/z targets and tolerance windows.

📥 Input
CSV file containing at least:Column Name	Description
Measured Mass	

⚙️ Method
Matches observed m/z values to predefined precursor list 
Applies ± tolerance window (default: 0.25 Da)
Tags matched rows with corresponding target m/z
Removes duplicates

📤 Output
CSV file containing:
matched precursor rows
Target_mz column indicating matched precursor

▶️ How to run
python src/extract_precursors.py

📌 Example output
station14_4000m_precursors.csv
