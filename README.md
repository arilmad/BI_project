# BI_project
Individual project in Business Intelligence and Analyzing Big Data at HEC UNIL 2020 spring.

__Key repository files to gain a quick overview__:

__`pdf` files__:
 * `Business_Intelligence_Presentation.pdf` is a very descriptive set of slides which aim to catch the essence of the project. Speed-read it and decide if you want to proceed to``Business_Intelligence_Project.pdf`. 
 * `Business_Intelligence_Project.pdf` presents the project problem, motivation, approaches, findings and figures over 16 pages.

__folders__:
 * `raw` is the first folder in the pipeline. This is the folder to which raw data recently fetched from its sources is dumped. These files usually require a few steps of preprocessing before they are ready to be processed in SQL.
 * `sql_src` contains data that is ready to be processed in SQL and further on loaded into suitable tables.
 * `sql_output` contains data that has been loaded and joined through SQL queries. This data is relevant for analysis, but may still contain missing and elsewise false values.
 * `cleansed_data` contains data that has been filtered and interpolated. These are complete time series that are ready for analyses.
 * `figures` contains a collection of image outputs, mostly from the `descriptive_analysis` script. 
 
__scripts__:
 * `frost_api_connector` connects to the Frost API and collects weather data. Outputs either as `.json` files or as `.csv` files.
 * `transform_*`-scripts contain the few lines required to move data from `raw` to `sql_src`.
 * `warehouse_builder` connects to a local MySQL database and constructs the warehouse based on data from `sql_src`. A few sample queries to the warehouse is also provided. Outputs relevant data to `sql_output`.
 * `cleanser` loads all time series from `sql_output` and performs various operations on the data in order to output complete and consistent data to `cleansed_data`.
 * `descriptive_analysis` loads data from `cleansed_data` and makes several aggregations and visualizations.
 * `granger_causality` loads data from `cleansed_data` and performs the Granger causality tests.
 * `apriori_miner` exploits the apriori algorithm in search for valuable association rules.
 
### Please note that this code has been developed for prototyping purposes, and is not necessarily user friendly.
![backend](https://raw.githubusercontent.com/arilmad/BI_project/master/figures/backend.jpg)
