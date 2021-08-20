## Analyzing data

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


## Common names we use for variables:

- `d`: data, the variable containing the dataframe of all trials
- `dl`: data long, the variable containing the dataframe of all trials in long format. 
