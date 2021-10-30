
# SARS-CoV-2 Serosurveillance Data by Serotracker

[SeroTracker](https://serotracker.com/en/Explore) synthesizes findings from thousands of COVID-19 seroprevalence studies worldwide, providing a data platform and interactive dashboard for SARS-CoV-2 serosurveillance. This dataset in this repository represents our collection of serosurveillance studies.

### Download
Our complete SARS-Cov-2 dataset can be downloaded programmatically at this URL `https://raw.githubusercontent.com/serotracker/sars-cov-2-data/main/serotracker_dataset.csv`.

Our dataset can also be downloaded directly from our [Airtable view]([https://airtable.com/shraXWPJ9Yu7ybowM/tbljN2mhRVfSlZv2d?backgroundColor=blue&viewControls=on](https://airtable.com/shraXWPJ9Yu7ybowM/tbljN2mhRVfSlZv2d?backgroundColor=blue&viewControls=on)). This option does not allow for programmatic downloads.

### Data Architecture
Our data is arranged hierarchically and consists of an article or document providing seroprevalence data (“source”), the “studies” reported within a given source, and the seroprevalence “estimates” derived from the studied population. Our CSV file is formatted to contain 1 row per estimate. Therefore, multiple rows may be associated with the same SARS-CoV-2 seroprevalence study and source.

A single source may contain multiple studies based on our definition of a serosurvey. Articles that do not report an overall seroprevalence estimate and provide information on two or more distinct cohorts (different sample frames, different samples at different time points, or non-overlapping geographic regions) without a pooled estimate were considered to be multiple studies. In these instances we extract a study record for each set of data and link extracted estimates to those individual studies. 

Each study contains a summary estimate of the seroprevalence of the entire population studied (largest denominator reported). We identify and extract the ‘primary estimate’ — the summary estimate that most accurately reflects the seroprevalence at the respective geography and time-point — for every study. Other summary estimates that may exist are extracted as a sub-group estimate. For more information on how we determine the primary estimate, refer to our [prioritization protocol](https://docs.google.com/document/d/16FUS1fr5F_KpWHTznXiprzXZB_hDr8z3URhh9Zr78M8/edit?usp=sharing).

A study may also contain several stratifying subgroup estimates such as age and sex. We extract subgroup estimates for age, sex, race, ethnicity, COVID-19 vaccination status, statistical analysis (population, test adjustment), and geographical area in general population sample frames. We document other subgroups present in a given study through the ‘subgroup variables available’ field. Our full list of subgroup options can be found [here](https://docs.google.com/document/d/16FUS1fr5F_KpWHTznXiprzXZB_hDr8z3URhh9Zr78M8/edit?usp=sharing). For more information on our general population sample frame classification, please visit [here](https://docs.google.com/document/d/16FUS1fr5F_KpWHTznXiprzXZB_hDr8z3URhh9Zr78M8/edit?usp=sharing). No subgroup estimates are extracted from special population studies. 

### Additional Information
Please see our [Data Dictionary](https://airtable.com/shrz0CXeuUxlbd0Rm) for explanations of our variables, data types, and descriptions as well as insight into how our data is collected by our research team.

In order to keep up to date with important changes to our dataset, please consult our [Change Log](https://airtable.com/shrxpAlF6v0LeRYkA/tblC6jj904WXUzwVY) regularly.

For more information about how we collect, extract and use our data, please see the [Data page](https://serotracker.com/en/Data) on our website.

If you have a SARS-CoV-2 seroprevalence study that has not yet been captured by serotracker.com, please submit the source using this [form](https://docs.google.com/forms/d/e/1FAIpQLSdvNJReektutfMT-5bOTjfnvaY_pMAy8mImpQBAW-3v7_B2Bg/viewform). Our research team will review each submission to evaluate whether it meets our inclusion criteria.

If you are open to being contacted about your use case for our data, please fill out this [form](https://forms.gle/gqi3kvKQgasYCrQE9). This helps us create datasets that are most useful to you.

Our data can be cited as this [Lancet Inf Dis article](https://www.thelancet.com/journals/laninf/article/PIIS1473-3099(20)30631-9/fulltext#%20).

### Change Log
- Oct 27, 2021: We created `serotracker_dataset.csv` containing the following columns: Prevalence Estimate Name, Rapid Review Study Name (Text), Source Name, Publication Date, Grade of Estimate Scope, Country, State/Province, City, Sampling Start Date, Sampling End Date, Sample Frame (groups of interest), Sample Frame (age), Age Minimum, Age Maximum, Sub-grouping Variable, Subgroup category for analysis, Sub-group specific category (clean), Denominator Value, Serum positive prevalence, Serum pos prevalence, 95pct CI Lower, Serum pos prevalence, 95pct CI Upper, Test Adjustment, Population Adjustment, Adjust serum positive prevalence, Adjusted serum pos prevalence, 95pct CI Lower, Adjusted serum pos prevalence, 95pct CI Upper, Adjusted sensitivity, Adjusted specificity, Independent evaluation type, Sampling Method, Test Manufacturer, Test Type, Test Validation, Isotype(s) Reported, Antibody target, Specimen Type, Sensitivity, Specificity, Overall Risk of Bias (JBI), JBI 1, JBI 2, JBI 3, JBI 4, JBI 5, JBI 6, JBI 7, JBI 8, JBI 9, Source Type, First Author Full Name, Lead Institution, UNITY: Criteria, URL, Date Created, Last modified time, Data Quality Status.