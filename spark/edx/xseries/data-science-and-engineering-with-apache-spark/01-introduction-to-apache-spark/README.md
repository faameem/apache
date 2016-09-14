# Test BerkeleyX: CS105x Introduction to Apache Spark #

## Welcome to CS 105.1x and Course Objectives/Prequisites ##

### Requirements ###
+ Python 2.7
+ PySpark (the Python API for Apache Spark)
+ Spark SQL (the SQL API for Apache Spark)
+ [Python mini quiz](http://www.mypythonquiz.com/)
+ [Python mini course](http://ai.berkeley.edu/tutorial.html#PythonBasics)

### Discussion Group ###
+ [Piazza discussion group](https://piazza.com/edx_berkeley/summer2016/cs1051x/home)
+ access code: cs1051x

### Course Lab Exercises ###
+ Use the free [Databricks Community Edition platform](https://accounts.cloud.databricks.com/registration.html#signup/community)
+ Google Chrome or Mozilla FireFox
+ By using the free platform, you will not need to install any Spark software on your machine. 
+ Databricks Community Edition provides a powerful, complete Spark environment that includes a mini 6GB cluster running on Amazon AWS, and interactive notebook environment with visualizations and dashboards, and public environment to share your work. 

## Sources of Big Data ##
+ [Awesome Public Datasets](https://github.com/caesar0301/awesome-public-datasets)
+ [ Structured Open Urban Data: Understanding the Landscape](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4174913/pdf/big.2014.0020.pdf) examines over 9,000 open data sets from 20 cities in North America
+ [San Francisco onlint city records](https://data.sfgov.org/) cover public safety, health, transportation, housing and many other topics:
    - In the health section of sf.data.gov there is an extensive set of records about restaurant inspections. San Francisco has the largest number of restaurants per capita of any major city in the United States. Tracking and maintaining the quality of those restaurants is an ongoing challenge for inspectors. An interesting question would be could you create an "early warning system" based on social media (e.g., is it possible to predict restaurants in need of inspection from Yelp reviews?)? This question could be partially answered by building a machine learning classifier using historical social media reviews (e.g., from Yelp or Trip Advisor) and city records of inspections.
    - The City receives many [3-1-1 reports](http://www.sf311.org/) (non-emergency incident reports from citizens). But some of these reports predict serious incidents, which may be recorded later in police reports. Consider the challenge of mining the CABLE reported incidents, and looking for text markers that predict future police reports. This challenge would require tying the two tabular datasets together, a process that is complicated by noisy data - would it be better to tie the datasets together by the name of the protagonist or the location (address) of the incident? This is an entity resolution problem, as the protagonists' names might be listed differently in the two datasets (e.g., Anthony Joseph versus A. Joseph), and the same applies to address information in the two datasets (e.g., SF City Hall versus 1 Dr Carlton B Goodlett Pl, San Francisco, CA 94102). You will explore the entity resolution problem in Lab #3.  After combining the two datasets, the next step would be to look for keywords in the police report marking the type of incident, and attempt to predict incidents from the full text of the CABLE report.

## Analysis, Big Data, and Apache Spark ##

+ [Blog post](https://databricks.com/blog/2016/05/24/genome-sequencing-in-a-nutshell.html) about [ADAM open source genomics pipeline](https://github.com/bigdatagenomics/adam). See and run your own ADAM genomics analysis on data from the 1000 Genomes project using this [notebook](http://cdn2.hubspot.net/hubfs/438089/notebooks/Samples/Miscellaneous/Genome_Variant_Analysis_using_k-means_ADAM_and_Apache_Spark.html).

+ Capital One also uses Spark and graph analysis to detect [fraudulent applications](https://spark-summit.org/2016/events/keynote-4-day-3/).

+ Another example of Big Data processing is [IBM's jStart team's work with the USA Cycling Women’s Team Pursuit team](http://www-01.ibm.com/software/ebusiness/jstart/portfolio/usacycling.html). The jStart team is using Spark Streaming to analyze streaming data from the riders' power meter, heart rate monitor and wearable muscle oxygen sensor, and provide coaches and riders with real-time performance metrics, such as W-prime depletion and matches burned.

## Apache Spark Transformations ##

### User Defined Functions ###

Note that UDFs in Python are slow, so whenever possible, consider using built-in functions instead. For example, instead of creating a lambda function and using a UDF  to subtract one from the values of a column, you should use a select transformation to perform the subtraction.
