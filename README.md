# analysis-r-template

The goal of this project is to centralize and make more efficient the process of analyzing data. To do this, we have created a data-to-analysis pipeline that is easy to replicate and follow across many different projects.
Duplicate this project and rename it in accordance with your own analysis.

Before you start analyzing any type of data in the lab you need to use this structure to process your files and analyze them.

This template will instruct you how to:

1. **Where to put your raw data:** Download all experiment data from AWS and save it **locally to your machine.**  In case your data comes from aws, the processing code includes some simple code that would help you download your data to the raw folder.
2. **Demonstrate how to format `R` code analyses**

This template contains the following folders:

- `0_processing`, which guides you through downloading data through AWS and then formatting the csv files to prepare for analysis
	- `download-processing.Rmd` is the `R` script that performs these actions.
	- `download-processing.html` is a printout of the script. We make these `.html` files because sometimes we do not want to run the entire `R` code just to see the outcome, plus they can be distributed without the raw data when we only need to see how the analysis was performed.
- `1_analysis`, which outlines how analyses should be formatted
	- `data-analysis.Rmd` is the `R` script that outlines how to analyze
	- `data-analysis.html` is the `html` printout of the above file
- `data`, which will autodownload the raw data files onto YOUR COMPUTER ONLY (if using AWS). There is a `.gitignore` set in this folder to prevent raw data files from being uploaded to GitHub. **The populated data folder should NEVER REACH THE GITHUB.**
