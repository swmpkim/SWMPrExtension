
![](swmpr_logo.png)
#### *Julie Padilla, jpadilla@limno.com*, [LimnoTech](www.limno.com)

[![Travis-CI Build Status](https://travis-ci.org/padilla410/SWMPrExtension.svg?branch=master)](https://travis-ci.org/padilla410/SWMPrExtension)

<!-- README.md is generated from README.Rmd. Please edit that file -->



# Overview 

The System Wide Monitoring Program ([SWMP](http://nerrs.noaa.gov/RCDefault.aspx?ID=18)) was implemented by the National Estuarine Research Reserve System ([NERRS](http://nerrs.noaa.gov/)) in 1995 to provide continuous monitoring data at over 140 continuous monitoring stations in 28 estuaries across the United States.  SWMPrExtension (pronounce "swamper extension") is an R package that provides additional functions to organize and analyze SWMP data and is intended as a companion package for [SWMPr](https://github.com/fawda123/SWMPr) (pronounced "swamper"). Currently, there is no citation for SWMPrExtension.

[SWMPr](https://github.com/fawda123/SWMPr) is an R package for retrieving, organizing, and analyzing estuary monitoring data from SWMP. SWMPr can be cited as follows:

*Beck MW. 2016. SWMPr: An R package for retrieving, organizing, and analyzing environmental data for estuaries.  The R Journal. 8(1):219-232. https://journal.r-project.org/archive/2016-1/beck.pdf*

# Installing the package

This package is not currently available on CRAN, but will be in the near future

The development (unstable) version of this package can be installed from Github:


```r
install.packages('devtools')
library(devtools)
install_github('padilla410/SWMPrExtension')
library(SWMPrExtension)
```

# Using the package

Documentation for SWMPrExtension is currently in development.

A quick summary of the SWMPr package can be found [here](https://github.com/fawda123/SWMPr). A detailed manuscript describing full use of the SWMPr package is available from the [R Journal](https://journal.r-project.org/archive/accepted/beck.pdf). All source materials for the manuscript are available [here](https://github.com/fawda123/swmpr_manu).

SWMPrExtension adds several functions to existing concepts in SWMPr and introduces a new concept called "Reporting".

<h3>Analyze</h3>
<table>
<tr><td><code>annual_range.swmpr</code></td><td>For a user-specified year, calculate averages, average ranges, and min/max observed ranges the on a monthly or seasonal basis</td></tr>
<tr><td><code>historical_daily_range.swmpr</code></td><td>Compare a user-specified year against historical data on a daily basis.</td></tr>
<tr><td><code>historical_range.swmpr</code></td><td>Compare a user-specified year against historical data on a monthly/seasonal basis.</td></tr>
<tr><td><code>raw_boxplot.swmpr</code></td><td>Generate a monthly/seasonal boxplots of raw data for a target year</td></tr>
<tr><td><code>seasonal_barplot.swmpr</code></td><td>Generate monthly/seasonal barplot for parameters that are better viewed in on a cumulative basis (e.g. precipitation).</td></tr>
<tr><td><code>seasonal_boxplot.swmpr</code></td><td>Generate monthly/seasonal boxplots for daily average statistics (min/average/max) across a user-specified time period.Includes the option to calculate a median value for a target year and include a line for a water quality threshold.</td></tr>
<tr><td><code>threshold_identification.swmpr</code></td><td>Identify dates and times that a user-specified water quality threshold is exceeded. For continuous monitoring data, the user can also specify the length of time the threshold must be exceeded for the event to be included (e.g. DO must be < 2 mg/L for at least 2 hours).</td></tr>
<tr><td><code>threshold_percentile_plot.swmpr</code></td><td>Compare raw data against user-specified percentiles calculated from historical data. User has the option to calculate percentiles on a monthly basis.</td></tr>
<tr><td><code>threshold_plot.swmpr</code></td><td>Compare raw data against user-specified water quality thresholds</td></tr>
<tr><td><code>threshold_summary.swmpr</code></td><td>Summarize the results from <code>threshold_identification</code> in either a plot or tabular format. Results can be aggregated on a monthly, seasonal, or annual basis.</td></tr>
<tr><td><code>res_local_map</code></td><td>Create a stylized reserve-level map for use with the reserve level reporting template</td></tr>
<tr><td><code>res_national_map</code></td><td>Create a base map for NERRS reserves in ggplot</td></tr>
<tr><td><code>res_sk_map</code></td><td>Create a stylized reserve-level map of seasonal kendall results for use with the reserve level reporting template</td></tr>
<tr><td><code>reserve_locs</code></td><td>Create a dataframe of selected NERRS locations for plotting with <code>res_national_map</code></td></tr>
<tr><td><code>seasonal_dot.swmpr</code></td><td>Plot average/min/max seasonal values faceted by season</td></tr>
<tr><td><code>sk_seasonal</code></td><td>Non-parametric test for monotonic seasonal trends</td></tr>
</table>

<h3>Retrieve</h3>
<table>
<tr><td><code>import_local_nut</code></td><td>A modified version of import_local from the <code>SWMPr</code> package. This version allows the user to specify the collection method (<code>CollMethd</code>) argument to separate monthly nutrient sampling data from monthly 24-hr nutrient sampling data.</td></tr>
</table>

<h3>Miscellaneous</h3>
<table>
<tr><td><code>assign_season</code></td><td>Assign seasons to SWMPr sampling data on a monthly basis or user-defined basis</td></tr>
<tr><td><code>load_shp_file</code></td><td>Load and format shapefile for use with res_local_map</td></tr>
<tr><td><code>lm_p_labs</code></td><td>Generate a dataframe of p-value labels based on p-values from linear regression</td></tr>
<tr><td><code>set_date_breaks</code></td><td>A helper function to select reasonable breaks for <code>scale_x_datetime</code></td></tr>
<tr><td><code>sk_tidy</code></td><td>Tidy results from <code>kendallSeasonalTrendTest</code></td></tr>
<tr><td><code>std_param_check</code></td><td>Determine if a parameter is one of the standard SWMP parameters</td></tr>
<tr><td><code>title_labeler</code></td><td>Generate a plot title based on SWMP station abbreviation</td></tr>
<tr><td><code>y_count_labeler</code></td><td>Generate a y-axis label based on SWMP parameter abbreviation and threshold criteria</td></tr>
<tr><td><code>y_labeler</code></td><td>Generate a y-axis label based on SWMP parameter abbreviation</td></tr>
</table>

<h3>Reporting</h3>
<table>
<tr><td><code>get_reserve</code></td><td>Return the full name of the reserve associated with the data files in the 'data' folder of the reserve level template</td></tr>
<tr><td><code>get_shp_name</code></td><td>Return the name of the shape file associated with the data files in the 'data' folder of the reserve level template</td></tr>
<tr><td><code>get_site_code</code></td><td>Return the 3 letter reserve code associated with the reserve</td></tr>
<tr><td><code>get_site_coordinates</code></td><td>Return the station coordinates for stations associated with the data files in the 'data' folder of the reserve level template</td></tr>
<tr><td><code>get_sites</code></td><td>Return the stations associated with the data files in 'data' folder of the reserve level template</td></tr>
</table>
