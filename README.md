# analysis-r-template

Amit - this part should include a reference table for the specific parts of this analysis. see for example : https://github.com/GoldenbergLab/lab-helper-codes/blob/main/guides/aws/s3-tasks/download.md - it should probably go under the purpose.





## Purpose: Amit - should this go before the reference table? not sure
The goal of this project is to centralize and make more efficient the process of analyzing data. To do this, we have created a data-to-analysis pipeline that is easy to replicate and follow across many different projects.
Duplicate this project and rename it in accordance with your own analysis.

Before you start analyzing any type of data in the lab you need to use this structure to process your files and analyze them.

This template will instruct you how to:

1. **Where to put your raw data:** In case your data comes from aws, the processing code includes some simple code that would help you download your data to the raw folder.

Amit - I think that the text below should move to readme in the processing folder. and there shoudl be a reference here.
 Download all experiment data from AWS and save it **locally to your machine.** If you are not using AWS to collect data, please follow the instructions in header 1b rather than 1a.

2. Demonstrate how to format `R` code analyses.


Amit- this read me should probably end here with a note that specific instructions are given inside each folder. I do think that we should include a short explanation of what's here. So for processing for example, is just a general description of what's in the folder.

This template contains the following folders:

- `0_processing`, which guides you through downloading data through AWS and then formatting the csv files to prepare for analysis
	- `download-processing.Rmd` is the `R` script that performs these actions.
	- `download-processing.html` is a printout of the script. We make these `.html` files because sometimes we do not want to run the entire `R` code just to see the outcome, plus they can be distributed without the raw data when we only need to see how the analysis was performed.
- `1_analysis`, which outlines how analyses should be formatted
	- `data-analysis` is the `R` script that outlines how to analyze
- `data`, which will autodownload the raw data files onto YOUR COMPUTER ONLY (if using AWS). There is a `.gitignore` set in this folder to prevent raw data files from being uploaded to GitHub. **The populated data folder should NEVER REACH THE GITHUB.**

#amit - this below should be moved to the processing readme file - it shoudl also be specified what to do if you have a raw data or if you want to transfer aws data. 

### Things you need:

- [AWS access key](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) (either generate your own via IAM or ask Zi)
- `R`, `aws.s3` package
- name of your experiment folder in aws

## Processing data (if using AWS)

0. Copy this repository as a new repository
1. Head to the `0_processing` folder and define `aws_folder` (line 17) as the name of your task folder
2. Follow the [documentation](https://cran.r-project.org/web/packages/aws.s3/readme/README.html) on `aws.s3` package to ensure that `R` can communicate with AWS. I was able to get this working by pasting the following code into the `R` console (sans `AWS_SESSION_TOKEN`).

	```
	Sys.setenv("AWS_ACCESS_KEY_ID" = "mykey",
           "AWS_SECRET_ACCESS_KEY" = "mysecretkey",
           "AWS_DEFAULT_REGION" = "us-east-1")
	```
3. Run the first chunk of the processing code. This will download all data files on to your machine. Note: the raw data files should **NEVER EVER** reach GitHub. They are meant to be stored locally on your computer only. This repository is preprogrammed to ignore everything in the `data/raw/` folder - **DO NOT CHANGE THAT!**
4. Examine the histogram and determine the cutoff point for complete versus incomplete files. If the file is incomplete, move it to te `did_not_finish` folder.

## 1b Processing data (if not using AWS)

0. Copy this repository as a new repository
1. Copy your raw data in to the data/raw folder
3. Eliminate files that are too small.
4. Proceed to analysis.

## 2 Analyzing data

0. Go to the `1_analysis` folder.
1. Load packages and finish formatting the `.csv` (if necessary)
2. Examine the distribution, average or other applicable metrics of the results of the experiment.
3. Examine the demographics of the participants.
4. Examine the main effect and other effects present in the experiment
5. Perform the power analysis (if necessary)
6. Create an `.html` document of your analysis for easy examination. To do this,

## Analysis Coding convention

- **Chunk 1 is reserved for downloading the data and load the packages.**
- **Variable names should clearly indicate what they refer to.** Rename unclear variables that are unclear.
- **Chunks should all be named.** You can name the chunk by typing the name after `r` on the first line of the chunk. So, to name a chunk `cats`, the first line of the chunk should say `{r cats}`
- Analyses should be **clearly** described in the chunk title, as well as in the heading above it.
- Each chunk should contain an **analysis** (typically an `LMER` or `GLMER`) followed by a **graph.**
- Graphs should be clearly labeled on titles, x-axis, and y-axis.
