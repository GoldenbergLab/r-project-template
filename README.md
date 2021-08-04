# analysis-r-template

## 0 Purpose:
The goal of this project is to centralize and make more efficient the process of analyzing data.

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
2. Follow the [documentation](https://cran.r-project.org/web/packages/aws.s3/readme/README.html) on `aws.s3` package to ensure that `R` can communicate with AWS.
3. 

