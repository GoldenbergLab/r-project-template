## Analyzing data

## Analysis Coding convention

- **Chunk 1 is reserved for downloading the data and load the packages.** This should be the place where you define all of the variables, and modify the data.
- **Every chunks should be named.** You can name the chunk by typing the name after `r` on the first line of the chunk. So, to name a chunk `cats`, the first line of the chunk should say `{r cats}`
- detail of the Analysis should be **clearly** described before the chunk. Summary of the results can be done below each chunk.
- **Dataframe Names** should be simple as they are commonly used. We often use `d` for a wide-format data and `dl` for longer-format data [see explanations of wide and long data here](https://en.wikipedia.org/wiki/Wide_and_narrow_data)

## Analysis process (outlined in the `.Rmd` file)
Analysis files often have a similar strcuture. Please try to follow this structure as much as possible.
1. The first chunk is usually reserved for package and data download, variable modification and final processing (hoping that most of the processing is done earlier).
2. Later chunks are often used to examine descriptives of the data, which include demographics, distributions of main variables ect.
3. Examine the main effect and other effects present in the experiment
4. Additional and exploratory analysi.
5. Power analysis (if necessary for future studies). 
