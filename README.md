# Talladega experiment: stream flow reduction effects on organic matter decomposition and fungal growth 
This code reproduces data processing and analysis for an experiiment where decomposition assays (leaf litter and cotton strips) were deployed in an intermittent stream flow reduction experiment following a BACI design (Before-After, Control-Impact) in an Alabama Piedmont forest. 

![alt text](https://ctbond.weebly.com/uploads/1/5/2/6/152638843/editor/d916b34a-3673-4737-b377-cdf6dce7e81e-1-105-c.jpeg?1743361241)

A small plywood dam was built and fitted with four flexible PVC drainage pipes to divert flow from an 85-m section of the stream. Sensors and decomposition assays were deployed in the drained reach and in an upstream reference reach. In each reach (Impact and Control), sensors and decomposition assays were deployed in one of two pools, two riffles, and two terrestrial/riparian areas adjacent to each reach.

Decomposition rates, fungal biomass accumulation, and changes in substrate stoichiometry (C: N: P) were compared in two types of decomposition assays: native leaf litter (Tulip poplar i.e. Liriodendron tulipifera), and standardized cotton fabric strips (Tiegs et. al. 2019, https://doi.org/10.1016/j.ecolind.2019.105466). 

The following code with reproduce all environmental data and decomposition assay data processing and analysis, with raw data used herein will be made available on Hydroshare (links incoming).

## Environmental Data:
We provide code for processing various streams of environmental data that will serve as metadata in the decomposition analysis.

### Sensors deployed with decomposition assays in a lower pool of the experimental reach
![alt text](https://ctbond.weebly.com/uploads/1/5/2/6/152638843/ip1-sensors_orig.png)

### STICs, Stream Temperature, Intermittency, and Conductivity loggers
We deployed 12 STIC loggers (Stream Temperature, Intermittency, and Conductivity sensors) along the experimental and control reaches (evenly divided between pools, riffles, and riparian zones along each reach. These sensors were set to collect temperature and conductivity data every 15 minutes from June 2, 2022, to October 17, 2022. The raw conductivity data were used to classify the timeseries into wet or dry readings at each timestep. Each .csv file is associated with a single site for a single year. Also included is a “ReadMe” file that includes author information, column descriptions, and site locations. More information can be found on the AIMS OSF site: https://osf.io/e7s9j/

In the STIC data processing folder Rmarkdown file `STIC_data_processing.Rmd` in the STICs follders has all the code for proceessing raw STIC data and generating average temperatures, relative conductivity (sensors not reliable for Specific conductivity), and to infer the presence or absence of water at each sensor location over time. For raw STIC data used in this analysis, please see the following reference: 
Bond, C. T., D. Peterson, N. Jones, K. Kuehn (2025). Talladega experiment (AIMS Approach IV) Stream Temperature, Intermittency, and Conductivity Data (AIMS_SE_TAL_approach4_STIC), HydroShare, http://www.hydroshare.org/resource/c1cbac78537248c0ad05e35742f6c8fa

The code generates mean daily temperatures for each STIC location over each incubation time period for the decomposition assays, which was used to calculated temperature-normalized decay rates. We also provide visualization of these data
![alt text](https://ctbond.weebly.com/uploads/1/5/2/6/152638843/screenshot-2025-03-31-at-11-32-45-am_orig.png)
Caption: Panels show combined temperature data for pools and riffles of the Impact and Control reaches. The colored blocks on the bottom represent the incubation periods of decomposition assays. Vertical lines with text indicate when the flow diversion began and when flow was restored after 4 weeks of diversion. Trendlines show generalized additive modal (GAM) fitted with geom_smooth in ggplot. 


### Dissolved oxygen sensors
A total of four dissolved oxygen probes were deployed: in pools in 1) the lower impact reach, 2) the upper impact reach, 3) the lower control reach, and 4) the uppr control reach. These recorded dissolved oxygen concentrations as well as temperature every 15 minutes. In the DO_sensor_data folder, we provide the code used to calculate mean and SD of dissolved oxygen over each incubation period at each sensor. We also generate figures showing that the flow reduction resulted in a substantial drop in DO in the impacted reach:

![alt text](https://ctbond.weebly.com/uploads/1/5/2/6/152638843/screenshot-2025-03-31-at-12-34-03-pm_orig.png)
Caption Dissolved oxygen data from the upstream control pool (CU), downstream control pool (CD), upstream impact pool (IU) and downstream impact pool (ID). Note that DO sensors were deployed about 1-week into the Before (t1) deployment phase due to logistical conflicts, but oxygen is assumed to be stable throughout this period.

### Rainfall data
In order to account for rainfall (which can affect moisture in terestrial habitats as well as flow conditions in the stream), we used a nearby weather station to capture rainfall data. In the weather folder, an R markdown document contains code used to estimate average daily rainfall over each incubation period, and to geneerate the following figure:

![alt text](https://ctbond.weebly.com/uploads/1/5/2/6/152638843/screenshot-2025-03-31-at-3-27-59-pm_orig.png)
Daily average rainfall by time period:
t1 = 6.77 mm per day
t2a = 6.00 mm per day
t2b = 6.61 mm per day
t3 = 6.95 mm per day
So, daily average rainfall was fairly stable (6-7 mm per day) throughout the study period. A more sophisticated hydrologist than I migh be able to get more out of this data...
