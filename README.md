# gospel-authoring
DNN applied over the Four-Gospel Corpus (RV60): The aim is to identify the most probable BOOK given some fragment.

The original data was extracted from: https://www.unoenelsenor.com.ar/biblia.htm and after was manually splited, extracting the books of interest for the project.

- 14/06/2020

At this point this project is built on two files:

1. generate.ipynb: This script takes care of the data extraction. It reads the TXT files (One per each gospel) and generates multiple CSV files stored in the 'processed/' folder. 

2. script.ipynb: The main script. It loads the CSVs, merge them in one only file. Also, creates the flow for the training using the fast.ai built-in functions. 

