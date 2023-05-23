# analysis-r-template

<!-- toc -->
- [Purpose](#purpose)
- [Get Started](#get-started)
    - [Create your own analysis repository](#create-your-analysis-repository-folder)
    - [Clone the repository to your local machine](#clone-the-repository-to-your-local-machine)
    - [Rename the r project file](#rename-the-r-project-file)
- [Repository Contents](#repository-contents)

<!-- tocstop -->

## Purpose

The goal of this template is to unify the process of analyzing data in the lab. To do this, we have created template that is easy to replicate and follow across many different projects. We expect this template to fit almost all kinds of analysis that we don in the lab.

This template will instruct you how to:

1. **Where to put your raw data:** Regardless of where the original data is coming from, all raw data should be located in the same folder. In case in which the data is in aws (many of our lab experiments come from there) you can find instructions on how to download all experiment data from AWS and save it **locally to your machine.**  
2. **Demonstrate how to format `R` code analyses**

## Get Started

### Use this template

To use this template, click the green `Use this template` button at the top of the page. It will ask you to:

- Choose the repository's username/organization name.
    - Please set the owner of your analysis template to our lab (`GoldenbergLab`).
    - All analysis repositories should start as public, unless indicated otherwise.
- Name the repository following the lab naming convention. Full guide on repository naming conventions can be found [here](https://github.com/GoldenbergLab/naming-conventions#repository-names). In short, github repositories are following this naming convention: `project-name-analysis`. So if your project is about counting kittens, your repository name is `counting-kittens-analysis`.
- Add a description of your project. Please include:
    1. Project Name
    2. Date of repository creation
    3. Your name, and the names of other who worked on it
    4. The purpose of the project and the main question you asked
    5. The source of the data for the analysis (Prolific, MTURK, Qualtrics, etc.)
- Once the repository is generated, you will be redirected to it.

### Clone the repository to your local machine

To connect (or clone) the analysis repository from GitHub (aka the internet) to your own computer, please go to the green `Code` button with a dropdown menu and do one of two things:

1. **Open with [GitHub Desktop](https://desktop.github.com/)** (for those with less coding experience)

- Please download GitHub desktop using the link above
- Click `Open with GitHub Desktop`, and pick a location in your personal file system to store it using the GitHub Desktop cloning interface. The default is `Documents\GitHub` (this is fine to use).
- The folder should appear now in `Documents\GitHub\your-repository-name`.
- If using Linux, see option 2.

2. **Command line using HTTPS method** (for those with more coding experience)

- If using Linux or prefer the command line, you will use the HTTPS-based URL from the Code dropdown menu. The URL will look like https://github.com/startyourlab/r-project-template.git.
- Click the clipboard icon to copy it. From within your projects directory in the terminal, run git clone ..., replacing the "..." with the URL you just copied.

### Rename the r project file
By now should have an r project file called `analysis-r-template.Rproj`. For further explanation on r project files see [Repository Contents](#repository-contents). The name of the project file should be identical to your repository name.

## Repository Contents
By now, you should have a repository containing the folder below. Notice that there is a **seperate readme** in each of these folders to further provides details on how it should be structured.

- `processing`, which guides you through handaling raw data, downloading it from AWS (if relevant) and then formatting the csv files to prepare for analysis
	- `download-processing.Rmd` is the `R` notebook that performs these actions.
	- `download-processing.html` is an html printout of the script that is revised every time you save the analysis file. We make these `.html` files because sometimes we do not want to run the entire `R` code just to see the outcome, plus they can be distributed without the raw data when we only need to see how the analysis was performed.
- `analysis`, which outlines how analyses should be formatted.
	- `data-analysis.Rmd` is the `R` script that outlines how to analyze.
	- `data-analysis.html` is the `html` printout of the above file.
- `data`, which will autodownload the raw data files onto YOUR COMPUTER ONLY (if using AWS). There is a `.gitignore` set in this folder to prevent raw data files from being uploaded to GitHub. **The populated data folder should NEVER REACH THE GITHUB.**
- `analysis-r-template.Rproj`, which is the r-project file. When openning an r session from a project:
  - A new R session (process) is started
  - The .Rprofile file in the project's main directory (if any) is sourced by R
  - The .RData file in the project's main directory is loaded (if project options indicate that it should be loaded).
  - The current working directory is set to the project directory.
  For further reading on r project see [here](https://support.rstudio.com/hc/en-us/articles/200526207-Using-Projects)
  
  ## Note on Groundhog
  
We use groundhog (https://groundhogr.com/) to manage our packages. Groundhog makes sure that our package versions are consistent with the current date. This way, everyone will be using packages from the same date to prevent any issues related to package versioning in future analyses. 

To use groundhog, please: 
(1) make sure that you have the latest version of R/ RStudio installed; 
(2) install RTools; 
(3) make sure that you are in a fresh R session. If you are using Windows, you may encounter some difficulties with package dependecies. 

We specify how to work around these issues in the code. 
