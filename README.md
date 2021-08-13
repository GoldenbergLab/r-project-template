# analysis-r-template

## 0 Purpose:
The goal of this project is to centralize and make more efficient the process of analyzing data. To do this, we have created an AWS-to-analysis pipeline that is easy to replicate and follow across many different projects.
Duplicate this project and rename it in accordance with your own analysis.

This template will: 

1. Download all experiment data from AWS and save it **locally to your machine.** 
2. Demonstrate how to format `R` code analyses

This template contains the following folders: 

- `0_processing`, which guides you through downloading data through AWS and then formatting the csv files to prepare for analysis
- `1_analysis`, which outlines how analyses should be formatted
- `data`, which will autodownload the raw data files onto YOUR COMPUTER ONLY. There is a `.gitignore` set in this folder to prevent raw data files from being uploaded to GitHub. **The populated data folder should NEVER REACH THE GITHUB.**

### Things you need:

- [AWS access key](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) (either generate your own via IAM or ask Zi)
- `R`, `aws.s3` package
- name of your experiment folder in aws

## 1 Processing data

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

## 2 Analyzing data

0. Go to the `1_analysis` folder.
1. (chunk 1) Load packages and finish formatting the `.csv` (if necessary)
2. (chunk 2) Examine the distribution, average or other applicable metrics of the results of the experiment.
3. (chunk 3) Examine the demographics of the participants.
4. (chunk 4-6) Examine the main effect and other effects present in the experiment
5. (chunk 7) Perform the power analysis (if necessary)

## Analysis Coding convention

- **Chunk 1 is reserved for downloading the data and load the packages.**
- **Chunks should all be named.** You can name the chunk by typing the name after `r` on the first line of the chunk. So, to name a chunk `cats`, the first line of the chunk should say `{r cats}`
- Analyses should be **clearly** described in the chunk title, as well as in the heading above it.
- **Variable names should clearly indicate what they refer to.** Rename unclear variables that are unclear.
- Graphs should be clearly labeled on titles, x-axis, and y-axis.

