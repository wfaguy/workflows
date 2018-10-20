# Autotiering with WFA
This pack will allow you to move volume around within the same cluster.
The move will be triggered based on performance and busy indicators.

The performance and busy indicators are calculated values.
* The performance indicator will tell you whether something is "slow" (higher value = slower)
* The busy indicator will tell you whether something is "busy" (higher value = busier)

# Content

The pack contains the following datasource :
* import performance data from OCUM
* import volume move information from OCUM
* import an excel configuration file

The pack contains the following workflows :
* setup
    * will install excel module
    * will copy sample configuration file to c:\temp
* move volume - trigger manually
    * will make suggestions for volume move
    * operator must choose manually
    * operator can manipulate threshold and tuning settings
* move volume - trigger automatically
    * no input, can be scheduled
* clear performance data
* export performance data to excel
* export autotiering history to excel

# Setup

* Import the dar file
* run the setup workflow
* complete configuration excel file (sample in c:\temp)
* implement the 3 datasources
* using manual workflow, tune settings to have required result
* use clean performance workflow, to re-apply some settings
* once the settings are ok, schedule the auto workflow

# Formula's

The indicators are calculated based on formula's

** performance indicator ** : avg_latency/latency_threshold*avg_latency_weight + highest_peak_in_hour/latency_threshold*peak_weight + peak_count_in_hour*peak_count_weight
** busy indicator ** : IOPS/GB*busy_weight

The indicators are calculated on the fly during performance info import.  Threshold & weight values are coming from configuration excel file (defaults), but can be overridden by custom values, using annotations in OCUM

# Performance info

Performance information is imported incrementally and is aggregated on the fly.  Data comes in as hourly information and get aggregated to daily and finally weekly information.
If the default and/or custom values (threshold & weights) need tuning.  You need to re-import performance data to view effect immediatly.

# Aggregate selection

Target aggregates are selected based on tiering numbers, coming from excel file (config file).  Aggregate capacity thresholds are also config file.





