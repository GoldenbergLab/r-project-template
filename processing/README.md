## Processing data (if using AWS)

1. Head to the `download-processing.Rmd` file and define `aws_folder` (line 17) as the name of your task folder
2. Follow the [documentation](https://cran.r-project.org/web/packages/aws.s3/readme/README.html) on `aws.s3` package to ensure that `R` can communicate with AWS. I was able to get this working by pasting the following code into the `R` console.

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