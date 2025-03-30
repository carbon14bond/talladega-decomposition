# Talladega experiment: stream flow reduction effects on organic matter decomposition and fungal growth 
This code reproduces data processing and analysis for an experiiment where decomposition assays (leaf litter and cotton strips) were deployed in an intermittent stream flow reduction experiment following a BACI design (Before-After, Control-Impact) in an Alabama Piedmont forest. 

![alt text](https://ctbond.weebly.com/uploads/1/5/2/6/152638843/editor/d916b34a-3673-4737-b377-cdf6dce7e81e-1-105-c.jpeg?1743361241)

A small plywood dam was built and fitted with four flexible PVC drainage pipes to divert flow from an 85-m section of the stream. Sensors and decomposition assays were deployed in the drained reach and in an upstream reference reach. In each reach (Impact and Control), sensors and decomposition assays were deployed in one of two pools, two riffles, and two terrestrial/riparian areas adjacent to each reach.

Decomposition rates, fungal biomass accumulation, and changes in substrate stoichiometry (C: N: P) were compared in two types of decomposition assays: native leaf litter (Tulip poplar i.e. Liriodendron tulipifera), and standardized cotton fabric strips (Tiegs et. al. 2019, https://doi.org/10.1016/j.ecolind.2019.105466). 

The following code with reproduce all environmental data and decomposition assay data processing and analysis, with raw data used herein will be made available on Hydroshare (links incoming).

### Environmental Data:

#### STICs, Stream Temperature, Intermittency, and Conductivity loggers
We deployed 12 STIC loggers (Stream Temperature, Intermittency, and Conductivity sensors) along the experimental and control reaches (evenly divided between pools, riffles, and riparian zones along each reach. These sensors were set to collect temperature and conductivity data every 15 minutes from June 2, 2022, to October 17, 2022. The raw conductivity data were used to classify the timeseries into wet or dry readings at each timestep. Each .csv file is associated with a single site for a single year. Also included is a “ReadMe” file that includes author information, column descriptions, and site locations. More information can be found on the AIMS OSF site: https://osf.io/e7s9j/

An Rmarkdown file in the STICs follders has all the code for proceessing raw STIC data and generating average temperatures, relative conductivity (sensors not reliable for Specific conductivity), and to infer the presence or absence of water at each sensor location over time. For raw STIC data used in this analysis, please see the following reference: 
Bond, C. T., D. Peterson, N. Jones, K. Kuehn (2025). Talladega experiment (AIMS Approach IV) Stream Temperature, Intermittency, and Conductivity Data (AIMS_SE_TAL_approach4_STIC), HydroShare, http://www.hydroshare.org/resource/c1cbac78537248c0ad05e35742f6c8fa

