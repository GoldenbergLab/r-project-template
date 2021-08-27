## Processing your data

The goal of the processing stage is to combine and modify raw data files (located in the data folder) into a comprehensible csv file (or files, depending on the need) that would be later used in the analysis

1. To get started copy your raw data in to the data/raw folder. Notice that these files would only be located on your local computer and not on the repo. Therefore you need to find a way to make sure that these files are backed up.

2. Once the raw data is in the right place, here are the things that are typically done during data processing:
 - get rid of incomplete or bad data.
 - remove unnecessary or duplicated columns.
 - rename variables to have clear names.
 - Define variables based on their type (factor, numeric ect.)


### download data if using AWS

We created a bit of code that would help you to directly download the raw data to the right place. However, in order to make this happen there are a few things that needed to be done first in the r commend unlike

Amit - here there shoudl be an explanation of the r commed line.
amit - before the head to the file it would be good to explain what is required rather than just say follow these insructions. We need to provide a basic explanation of what is this commend line and why are we doing this. 

1. Head to the `download-processing.Rmd` file and define `aws_folder` (line 17) as the name of your task folder
2. Follow the [documentation](https://cran.r-project.org/web/packages/aws.s3/readme/README.html) on `aws.s3` package to ensure that `R` can communicate with AWS. I was able to get this working by pasting the following code into the `R` console.

	```
	Sys.setenv("AWS_ACCESS_KEY_ID" = "mykey",
           "AWS_SECRET_ACCESS_KEY" = "mysecretkey",
           "AWS_DEFAULT_REGION" = "us-east-1")
	```
3. Run the first chunk of the processing code. This will download all data files on to your machine. Note: the raw data files should **NEVER EVER** reach GitHub. They are meant to be stored locally on your computer only. This repository is preprogrammed to ignore everything in the `data/raw/` folder - **DO NOT CHANGE THAT!**
4. Examine the histogram and determine the cutoff point for complete versus incomplete files. If the file is incomplete, move it to te `did_not_finish` folder.
