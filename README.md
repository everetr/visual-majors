# The Visual Guide to Picking a College Major

## About

I visualize earnings, employment, and demographic info for all college majors in 
the US, using the 2015, 2016, and 2017 American Community Survey 1-year Public 
Micro Use Samples 
[(PUMS)](https://www.census.gov/programs-surveys/acs/technical-documentation/pums/documentation.html), 
obtained via [IPUMS](https://usa.ipums.org/usa/). 
This project was inspired by a 2014 FiveThirtyEight 
[article](https://fivethirtyeight.com/features/the-economic-guide-to-picking-a-college-major/) 
by @BenCasselman). Casselman used the 
2010-12 3-year PUMS, covering a period when the US economy was still meekly 
recovering from the Great Recession. This data can be accessed via the 
[`fivethirtyeight` package](https://github.com/fivethirtyeight/data/tree/master/college-majors). 
The current project uses more recent data spanning the succeeding period of 
stronger economic expansion.

**Note:** This is purely a descriptive exercise. No one should infer causality 
from these results. Rather, use them to get a general sense of student outcomes 
after graduation. The Handbook of the Economics of Education has an 
[excellent, exhaustive chapter](https://www.sciencedirect.com/science/article/pii/B9780444634597000075) 
summarizing the research on the causal effect of college major on labor market 
outcomes (
[earlier draft freely available via NBER](www.amaurel.net/IMG/pdf/w21655.pdf)).

Also, be aware that many majors don't have enough observations for one to be 
very confident in their estimates of earnings, unemployment, etc. Again, you 
should use these visuals to get a general sense of how majors compare (Library 
Science probably still earns less than Civil Engineering, on average, despite 
the uncertainty in the estimates) but don't get too caught up on the exact 
levels of each variable for the less popular majors. E.g., Petroleum Engineering has gigantic median earnings but very few people major in it.

## Data

The base dataset consists of 2,589,149 rows. I got this by excluding (From the raw PUMS dataset) non-civilians, those younger than 22, those without at least a bachelor's degree, and those for which no information on college major was reported. I then aggregated this individual-level dataset into major-level datasets. There are 173 majors (FO1P) in total, but I dropped majors which had too few people. Refer to `process_pums.R` and `compile_data.R` to see all of the exclusions and decisions I made while processing this data.

## Results

The processed datasets I used to make the following visualizations are available 
in `./data/processed/`. Explore them and 
[tell me](https://twitter.com/TheRealEveret) what you find. My inbox is open to
anyone with questions and/or feedback.

![Median Full-time Earnings by Major](/graphics/bar_med_ftyr_earn.png)

## License

Licensed under the General Public License version 3.0 (GPLv3.0). Some data I 
used cannot be provided.

## Extra Thanks

IPUMS took the ACS data, cleaned it, recoded it, extensively documented it, and
much more. Here is their full citation:

>Steven Ruggles, Sarah Flood, Ronald Goeken, Josiah Grover, Erin Meyer, Jose Pacas, and Matthew Sobek. IPUMS USA: Version 8.0 [dataset]. Minneapolis, MN: IPUMS, 2018. https://doi.org/10.18128/D010.V8.0

This wouldn't have been possible for me without @BenCasselman's 
[code](https://github.com/fivethirtyeight/data/blob/master/college-majors/college-majors-rscript.R). 
Reading and modifying it taught me R for the first time. Please check out his
work.

## Links

I work in a crowded space. Here are other people and orgs doing similar work on college majors.

* *[The Labor Market for Recent College Graduates](https://www.newyorkfed.org/research/college-labor-market/index.html)* (2018) by the New York Fed.

* *[Lifetime Earnings By College Major](https://public.tableau.com/profile/douglas.webber#!/vizhome/LifetimeEarnings/Sheet1)* (2018) by Dr. [Doug Webber](https://twitter.com/dougwebberecon) of Temple University. [Here](https://docs.google.com/viewer?url=http%3A%2F%2Fwww.doug-webber.com%2Fexpected_all.pdf&pdf=true) are the accompanying papers.

* *[Putting Your Major to Work: Career Paths after College](http://www.hamiltonproject.org/charts/median_earnings_for_largest_occupations)* (2017) by The Hamilton Project.

* *[The Economic Value of College Majors](https://cew.georgetown.edu/cew-reports/valueofcollegemajors/#full-report)* (2015) by the Center on Education and the Workforce at Georgetown University.

## Further Reading

* *[The Analysis of Field Choice in College and Graduate School: Determinants and Wage Effects](https://docs.google.com/viewer?url=http%3A%2F%2Fwww.amaurel.net%2FIMG%2Fpdf%2Fw21655.pdf&pdf=true)* (2015) by Altonji et al. NBER.

* *[The Economic Guide to Picking a College Major](https://fivethirtyeight.com/features/the-economic-guide-to-picking-a-college-major/)* (2014) by Ben Casselman. FiveThirtyEight.
