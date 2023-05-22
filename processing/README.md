## Processing your data

This stage combines and RAW data files (located in the data folder) into ONE comprehensible csv file (or files, depending on the need) to be later used in the analysis. You need to do the following things in order to accomplish this: 

  1. Download experiment data files from AWS
  2. Select the incomplete files based on file size
  3. Moves the incomplete files to a separate folder from the main data folder

A brief tutorial on the code `download-processing.Rmd` to do this is below. If you can't run the code chunks, you can also do this manually. Tutorial here: https://github.com/GoldenbergLab/lab-helper-codes/blob/main/guides/aws/s3-tasks/download.md

### Download data (AWS)

If you are using AWS, this code directly downloads the raw data from AWS to the data folder. To do this, there are a few things that needed to be done first in the `R` console, which is located beneath your `R` code. It should be labeled `console` at the top left. We will input our AWS key into this console. The AWS key is a set of credentials that allows the `R` software on your computer to connect with the AWS server online. Inputting the credentials into the `R` console saves them into your `R` environement space (which means you won't have to input them again after doing this once).

1. Head to the `download-processing.Rmd` file and define `aws_folder` (line 17) as the name of your task folder
2. Follow the [documentation](https://cran.r-project.org/web/packages/aws.s3/readme/README.html) on `aws.s3` package to ensure that `R` can communicate with AWS. I was able to get this working by pasting the following code into the `R` console.

	```
	Sys.setenv("AWS_ACCESS_KEY_ID" = "mykey",
           "AWS_SECRET_ACCESS_KEY" = "mysecretkey",
           "AWS_DEFAULT_REGION" = "us-east-1")
	```
3. Run the first chunk of the processing code. This will download all data files on to your machine. Note: the raw data files should **NEVER EVER** reach GitHub. They are meant to be stored locally on your computer only. This repository is preprogrammed to ignore everything in the `data/raw/` folder - **DO NOT CHANGE THAT!**
4. Examine the histogram and determine the cutoff point for complete versus incomplete files. If the file is incomplete, move it to te `did_not_finish` folder.

### Processing data

Once the raw data is in the right place (and incomplete files are removed), here are the things that are typically done during data processing:
 - get rid of incomplete or bad data.
 - remove unnecessary or duplicated columns.
 - rename variables to have clear names. These should be names that would be clear to someone who doesn't know the details of the project. See [naming conventions](https://github.com/GoldenbergLab/naming-conventions) for further detail on naming variables. 
 - Define variables based on their type (factor, numeric ect.)
