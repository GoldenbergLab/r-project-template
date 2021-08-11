# analysis-r-template

## 0 Purpose:
The goal of this project is to centralize and make more efficient the process of analyzing data. 
Duplicate this project and rename it in accordance with your own analysis.

This template will: 

1. Download all experiment data from AWS 
2. Demonstrate how to format `R` code analyses

### Things you need:

- AWS API key (either generate your own via IAM or ask Zi)
- `R`, `aws.s3` package
- name of your experiment folder in aws

## 1 Processing data

0. Copy this repository as a new repository
1. Head to the `processing` folder and define `aws_folder` (line 15) as the name of your task folder
2. Follow the [documentation](https://cran.r-project.org/web/packages/aws.s3/readme/README.html) on `aws.s3` package to ensure that `R` can communicate with AWS. I was able to get this working but pasting the following code into the `R` console (sans `AWS_SESSION_TOKEN`).
    
	```
	Sys.setenv("AWS_ACCESS_KEY_ID" = "mykey",
           "AWS_SECRET_ACCESS_KEY" = "mysecretkey",
           "AWS_DEFAULT_REGION" = "us-east-1")
	```
3. Run line 18 of the processing code. Note: the raw data files should **NEVER EVER** reach GitHub. They are meant to be stored locally on your computer only. This repository is preprogrammed to ignore everything in the `data/raw/` folder - **DO NOT CHANGE THAT!**

