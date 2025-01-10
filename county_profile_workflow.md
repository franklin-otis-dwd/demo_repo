# County Profiles R Process

R is a useful tool to keep help me reproduce my steps for the source data. It means I can go back to my R script and see any comments I wrote. In one place, I can see all of the data, where it came from (I try to write helpful comments!), and what I did to clean and manipulate the data. R, like all programming languages, is great at iterative and repetitive tasks.  

RMarkdown/Quarto is a language that can be used create reports in RStudio. It is useful for documents because you can keep all of your sources in one place: data, text, code, images. This can be really powerful and create some really great-looking documents (PDF, HTML documents, dashboards, Word docs). 


## Problem:
OEA needs to make 72 reports every two years, one for each county. 
These documents all have the same source data, but will have very contextual narrative that each regional economist writes. This process can be repetitive, especially if there's manual touches involved in graphics and layout. 
Collating, joining, and cleaning data from various sources can be tricky. 

## Workflow: 
 -	Collate, clean, combine, and document data sources with R scripts. Save the cleaned data as RData, a heavily compressed R-specific data file. 
 -	Create a document template document using RMarkdown/Quarto. This template can take input parameters, which would be the specific county we want. 
		- This template has a couple of sentences and some definitions for each section of the report. 
		- Graphs, another powerful tool in R
 -	Iterate through each county to generate a Word document based on the template. 
 -	Send the Word documents to each OEA writer to add in their local knowledge and add context. 
 -	Load the text from the Word documents back into R to generate the final PDFs using a different template. 

## What worked:
 -	R for manipulating data was great. When writers had questions about the data, I was able to refer to my notes to see what I did. It really helped with organization.
 -	Creating a Word doc template for writers helped kickstart the writing process and cut down on some of the drudgery in writing. No longer did writers have to manually plug in the unemployment rate for Dodge County in their writing. 
 -	The final(ish) documents look pretty good!

## What was a pain:
 -  Creating the template documents was very tedious. Was it more tedious than doing it manually? No, but there was a lot of trial and error on my end.
 -  Final document formatting was a learning process and involved a lot of trial and error. PDFs are generated behind the scenes using this system called LaTeX, which is very powerful and configurable, but just as arcane and finicky.  
 - No great way of dealing with Word's track changes. All of the writing, editing and changing has to be done manually with Word.

## Resources that were invaluable:
 -	Google and Stack Overflow
 -	[Quarto Documentation](https://quarto.org/docs/guide/)
 -	[R Cheat Sheets](https://posit.co/resources/cheatsheets/)
 		- Particularly stringr, purrr, tidyr, data visualization, and dplyr
 -	This diagram with names for how to customize each element in GGPlot: [https://henrywang.nl/ggplot2-theme-elements-demonstration/](https://henrywang.nl/ggplot2-theme-elements-demonstration/)
