# GlacierMIP4 Experimental Protocol

**GlacierMIP4** is a community effort to project the future global glacier mass change and corresponding sea-level contribution of all glaciers on Earth outside the ice sheets using different glacier models with a focus on informing the IPCC's Seventh Assessment Report (AR7). In addition, we aim to analyse inter-model differences by examining the individual components of simulated mass balances (accumulation, melt, runoff, refreezing, frontal ablation).

The **GlacierMIP4 protocol** defines the experimental design for GlacierMIP4 and aims to standardize the experimental setups for glacier model simulation, using standardized time periods and datasets to initialize and force the glacier models.

---

# Table of contents

  - [1. Who can participate in GlacierMIP4?](#1-who-can-participate-in-glaciermip4)
  - [2. Submission deadline](#2-submission-deadline)
  - [3. Standardization of simulations](#3-standardization-of-simulations)
    - [Domain](#domain)
    - [Model period](#model-period)
    - [Inventory data](#inventory-data)
    - [Climate data for hindcast and projections](#climate-data-for-hindcast-and-projections)
    - [Prescribed variables](#prescribed-variables)
    - [Model calibration and validation](#model-calibration-and-validation)
  - [4. Requested output](#4-requested-output)
    - [Required variables](#required-variables)
      - [Annual variables](#annual-variables)
      - [Monthly variables](#monthly-variables)
    - [Sign convention](#sign-convention)
    - [File format and naming conventions](#file-format-and-naming-conventions)
      - [Regional files for each RGI region (mandatory)](#regional-files-for-each-rgi-region-mandatory)
      - [Regional files with Individual-glacier output for each RGI region (optional)](#regional-files-with-individual-glacier-output-for-each-rgi-region-optional)
  - [Contributors](#contributors)
  - [Contacts](#contacts)
  - [Authorship on GLACIERMIP4 publications](#authorship-on-glaciermip4-publications)

---

## 1. Who can participate in GlacierMIP4?

To participate in GlacierMIP4, you must contribute a unique dataset of global or regional-scale glacier projections. Projections must cover at least one full region of the Randolph Glacier Inventory (RGI) and be forced by the full set of prescribed climate scenarios. The projections must follow the GlacierMIP protocol.

Submissions utilizing the same model framework (e.g., OGGM, PyGEM, IGM) are welcome; however, they must exhibit significant differences from one another. This could include variations in model physics, calibration procedures, or other substantial aspects. Please reach out to us if you plan to submit projections using any of the openly available models (OGGM, PyGEM, IGM, GloGEM) but you are not part of the original developer group. Submissions from groups other than the developer group must be pre-approved by the GlacierMP core team to make sure they are sufficiently different from the projections from the developer group.

Data submissions will not be included if they fail to meet basic quality standards (e.g. results are not plausible, unrealistic or incomplete) or the model is deemed not suitable for the exercise.

By submitting to GlacierMIP4 you agree that your data may be visually displayed to other participants and the wider community (e.g. in plots during conferences) prior to publication. You also agree that your submitted data are made publicly available if included in GlacierMIP4 resulting publications. Some institutions demand internal institutional pre-approval of a paper submission to be listed as co-author. Please be aware that by submitting your data, you consent to its inclusion in the paper submission, even if you do not obtain the necessary pre-approval for being listed as co-author in time. This procedure is essential, as we cannot remove your projections shortly before the paper is submitted.

If you would like to participate, please indicate your intention by filling in this [survey ⚠️**TBD**⚠️](#) which also prompts for details about your model.

---

## 2. Submission deadline

The projections must be submitted in the prescribed format and received latest on **1 August 2026**. Since our planning is tied to the **IPCC AR7 schedule**, we will not accept late submissions.

---

## 3. Standardization of simulations

### Domain

Participants should, if possible, submit data for all RGI regions but submissions for at least one complete RGI region are also accepted.

### Model period

- Hindcast / calibration period: **2000–2025** (**end date may be adjusted pending IPCC decisions**).
- Projection period: **2025–2100** (or 2300 for some GCMs where specified).

Glacier models may apply a dynamic spin-up and can therefore begin their simulations prior to the year 2000, but modelers should provide all mandatory output (see **Table 3**) from the year 2000 onwards and until the end of the projection period (year 2100 or 2300 depending on the climate model data).

### Inventory data

- **Glacier outlines and area**: [RGI7](https://www.glims.org/rgi_user_guide/welcome.html).
- **Ice thickness**: Datasets are still under discussion but include the one by [Maffezzoli et al.](https://arxiv.org/abs/2512.11685). Alternatively, the thicknesses may also be provided in raster format based on reconstructions from OGGM and GloGEM. Initial ice volumes will be supplied both at the individual-glacier level and aggregated by RGI region. Modelers may either adopt these provided initial volumes directly or generate their own year-2000 volumes using model-specific spin-up procedures. In the latter case, the resulting regional ice volumes must agree with the reference values in **Table 1** within (⚠️**TBD ±10%**⚠️).

**Table 1.** Regional glacier area and volume. Areas are from RGI Consortium (2023) and volumes are from Maffezzoli et al (2026).

| Region | Full name | Area (km²) | Volume (km³) |
|:-------|:----------------------------------|------------:|:------:|
| 01 | Alaska | 86708 | **TBD** |
| 02 | Western Canada and USA | 14521 | **TBD** |
| 03 | Arctic Canada North | 105370 | **TBD** |
| 04 | Arctic Canada South | 40538 | **TBD** |
| 05 | Greenland Periphery | 90482 | **TBD** |
| 06 | Iceland | 11060 | **TBD** |
| 07 | Svalbard and Jan Mayen | 33959 | **TBD** |
| 08 | Scandinavia | 2948 | **TBD** |
| 09 | Russian Arctic | 51595 | **TBD** |
| 10 | North Asia | 2643 | **TBD** |
| 11 | Central Europe | 2124 | **TBD** |
| 12 | Caucasus and Middle East | 1407 | **TBD** |
| 13 | Central Asia | 50344 | **TBD** |
| 14 | South Asia West | 33075 | **TBD** |
| 15 | South Asia East | 16049 | **TBD** |
| 16 | Low Latitudes | 1929 | **TBD** |
| 17 | Southern Andes | 27674 | **TBD** |
| 18 | New Zealand | 886 | **TBD** |
| 19 | Subantarctic and Antarctic Islands | 133432 | **TBD** |
| Global |  | 706744 | **TBD** |

### Climate data for hindcast and projections

- **Hindcast**: To ensure consistency in the forcing data used across glacier models, all models must be run with ERA5 reanalysis fields and provide output for the calibration period 2000–2025 (note, the end date is still ⚠️**TBD**⚠️).
- **Projections**: All models must force their models with bias-corrected CMIP6 GCM data from eight GCMs (**Table 2**) and five SSP scenarios (SSP1-2.6, SSP5-3.4OS, SSP5-3.70,  SSP5-8.5 and the overshoot scenario SSP5-3.4OS). Scenarios and GCMs were selected to align as much as possible with the protocols used by [ISMIP](https://www.ismip.org/). We include the two GCMs used by ISMIP and selected additional GCMs based on [Snyder et al. (2024)](https://doi.org/10.5194/esd-15-1301-2024) which cover a wide range of climate sensitivities.
We will **bias-correct** monthly temperature and precipitation of all GCM projections to the ERA5 reanalysis, and the data will be made available to all participants. The bias-correction follows the method by ⚠️**TBD**⚠️. If you need additional variables or use a different time resolution you will need to prepare the data and bias-correct the GCM data yourself.

**Table 2.** List of the selected GCMs following [Snyder et al. (2024)](https://doi.org/10.5194/esd-15-1301-2024). Values in parentheses are Equilibrium Climate Sensitivity (ECS), and stars (*) indicate models with simulation until 2300. IPSL-CM6A-LR is one of the "hot models" ([Hausfather et al. 2022](https://doi.org/10.1038/d41586-022-01192-2)).

| Model | ECS | Until 2300 (*) | 
|---|---:|:---:|
| IPSL-CM6A-LR | 4.6 | * | 
| ACCESS-ESM1-5 | 3.9 | * |  
| BCC-CSM2-MR | 3.0 |  |  
| CESM-WACCM | 4.68 | * |  
| MRI-ESM2-0 | 3.2 | * |  
| MPI-ESM1-2-0 | 3.0 |  |  
| MIROC6 | 2.6 |  |  
| NorESM2-MM | 2.49 |  |  


### Prescribed variables / constants

Density conversion mass to volume in simulations: **900 kg m⁻³**

### Model calibration and validation

The glacier models are free to choose their own calibration and validation procedures and data, for example:

- Glacier-wide specific geodetic mass balances derived from an RGI7 updated version of **Hugonnet et al. (2021)** (Data will be provided but they are not finalized yet ⚠️**TBD**⚠️). 
- **WGMS** glacier-wide and point balances
- **GRACE** data
- **Snowline** data

---
### Where to download the data:
⚠️**TBD**⚠️

---

## 4. Requested output

GlacierMIP4 adopts a fully standardized output structure following the cf [metadata conventions](https://cfconventions.org/). Time intervals are specified via boundary variables and [cell methods](https://cfconventions.org/Data/cf-conventions/cf-conventions-1.7/build/ch07s03.html) attributes. All output must follow the variable definitions, units, sign convention, cf cell methods and metadata described below.

Some variables are only requested once per year, others once per month. Therefore, we request **two separate files per simulation**.

For each model and each RGI region submit:
- **Hindcast** (2000–2025):
  - 1 NetCDF file with annual variables
  - 1 NetCDF file with monthly variables
- For each **projection** (each GCM × each SSP) for the projection period (2025–2100/2300):
  - 1 NetCDF file with annual variables
  - 1 NetCDF file with monthly variables

Participants must submit the mandatory variables listed below for at least one complete RGI region. 

Optionally, participants may also submit additional files with results for each individual glacier within a RGI region. In this case the mandatory variables (see next section and **Tables 3 and 4**) must be included for every glacier.


## Mandatory output variables

### Annual variables:
- a) **Glacier area**
- b) **Glacier mass**
- c) **Glacier mass below sea level**
- d) **Frontal ablation**

If not computed, NaN values (⚠️**TBD**⚠️) must be given. Variables (a-c) are provided as state variables at the start of the year. Frontal ablation is given as a total over the preceding year as defined in variable time (see below).

### Monthly variables:
- **Accumulation, melt and refreezing over the evolving glacierized area** (sum over each month)
- **Glacier runoff** (glacier melt - refreezing + liquid precipitation) over the evolving glacierized area (“moving-gauge” runoff)
- **Precipitation over the initial glacierized area** (sum over each month)
- **Near-surface air temperature over the initial glacierized area** (area-weighted mean)

Variables (a) will be used to investigate inter-model differences in mass-balance components, while variables (c) and (d) will be used to examine differences in forcing after model-specific downscaling and corrections.

---

### Time definition (annual and monthly variables):
**Time** (start of year/month, in “days since 1850-01-01”)

### Domain definition (only for submissions with individual glacier output):
**RGI-Id** (of RGI glacier).

---
The full variable list for annual and monthly data with definitions and metadata is given in **Tables 3 and 4**.

### Table 3. Mandatory variables (annual output for entire RGI regions)

| <sub>Variable</sub> | <sub>Short name</sub> | <sub>Long name</sub> | <sub>Unit</sub> | <sub>Data type</sub> | <sub>Cell method</sub> | <sub>Temporal res.</sub> | <sub>Notes &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</sub> |
|---|---|---|---|---|---|---|:---|
| <sub>**Area**</sub> | <sub>`area`</sub> | <sub>Glacier area</sub> | <sub>m²</sub> | <sub>float32</sub> | <sub>point</sub> | <sub>annual</sub> | <sub>Glacier area at the start of the year.</sub> |
| <sub>**Mass**</sub> | <sub>`mass`</sub> | <sub>Glacier mass</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>point</sub> | <sub>annual</sub> | <sub>Total glacier mass at start of the year.</sub> |
| <sub>**Mass below sea level**</sub> | <sub>`mass_bsl`</sub> | <sub>Glacier mass below sea level</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>point</sub> | <sub>annual</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Glacier mass below sea level of tidewater glaciers at start of the year. Needed for conversion to sea-level rise.</sub></details> |
| <sub>**Frontal ablation**</sub> | <sub>`frontal_abl`</sub> | <sub>Total annual frontal ablation</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>sum</sub> | <sub>annual</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Frontal ablation of marine- and lake-terminating glaciers (mass losses from calving, subaerial frontal melting, sublimation above the waterline and subaqueous frontal melting below the waterline) over the preceding year; positive values indicate mass loss. If not calculated put NaN.</sub></details> |
| <sub>**Time (nc-axis)**</sub> | <sub>`time`</sub> | <sub>time</sub> | <sub>days since 1850</sub> | <sub>long</sub> | <sub>—</sub> | <sub>annual</sub> | <sub>Start of the year.</sub> |
| <sub>**ID (nc-axis, optional)**</sub> | <sub>`RGIId`</sub> | <sub>Randolph Glacier Inventory ID</sub> | <sub>—</sub> | <sub>String</sub> | <sub>—</sub> | <sub>—</sub> | <sub>ID of glacier in the Randolph Glacier Inventory (RGI 7). Only for individual glacier submissions.</sub> |

### Table 4. Mandatory variables (monthly output for entire RGI regions)

| <sub>Variable</sub> | <sub>Short name</sub> | <sub>Long name</sub> | <sub>Unit</sub> | <sub>Data type</sub> | <sub>Cell method</sub> | <sub>Temporal res.</sub> | <sub>Notes &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</sub> |
|---|---|---|---|---|---|---|:---|
| <sub>**Accumulation**</sub> | <sub>`acc`</sub> | <sub>Total accumulation</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>sum</sub> | <sub>monthly</sub> | <sub>Mass added to the glacier except for refreezing.</sub> |
| <sub>**Melt**</sub> | <sub>`melt`</sub> | <sub>Total glacier melt (snow, ice, firn)</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>sum</sub> | <sub>monthly</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Mass removed from the glacier except for frontal ablation (e.g., melt, evaporation). Melt is reported as positive values.</sub> |
| <sub>**Refreezing**</sub> | <sub>`refreeze`</sub> | <sub>Total refreezing</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>sum</sub> | <sub>monthly</sub> | <sub>If not calculated put NaN. Total refreezing within the snowpack or glacier.</sub> |
| <sub>**Runoff**</sub> | <sub>`runoff_glac`</sub> | <sub>Glacier runoff from glacierized area</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>sum</sub> | <sub>monthly</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Glacier runoff over the evolving glacierized area, defined as melt minus refreezing plus liquid precipitation. The values represent “moving-gauge” glacier runoff.</sub> |
| <sub>**Precipitation**</sub> | <sub>`precip`</sub> | <sub>Total precipitation over initial glacierized area</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>sum</sub> | <sub>monthly</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub> Total precipitation over the initial (year 2000) glacierized area after possible downscaling of climate input data (e.g., applying precipitation correction factors and gradients). This represents the actual precipitation values used in the accumulation calculations, with spatial averages area-weighted based on elevation-dependent or grid-based simulations. The purpose is to evaluate in how far model differences result from different downscaled precipitation.</sub></details> |
| <sub>**Temperature**</sub> | <sub>`temp`</sub> | <sub>Near-surface air temperature over initial glacierized area</sub> | <sub>K</sub> | <sub>float32</sub> | <sub>mean</sub> | <sub>monthly</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub> Mean near-surface (2 m) area-weighted air temperature over the initial glacierized area (year 2000) after possible downscaling of climate input data (e.g., application of bias-correction or lapse rate). This represents the actual temperature values used in the melt calculations and the separation of solid and liquid precipitation. Note, that temperatures must be area-weighted: for each spatial element (elevation band or grid cell), use the temperature weighted by that element’s area (year 2000). The purpose is to evaluate in how far model differences result from different downscaled air temperatures.</sub></details> |
| <sub>**Time (nc-axis)**</sub> | <sub>`time`</sub> | <sub>time</sub> | <sub>days since 1850</sub> | <sub>long</sub> | <sub>—</sub> | <sub>monthly</sub> | <sub>Start of the month.</sub> |
| <sub>**ID (nc-axis, optional)**</sub> | <sub>`RGIId`</sub> | <sub>Randolph Glacier Inventory ID</sub> | <sub>—</sub> | <sub>String</sub> | <sub>—</sub> | <sub>—</sub> | <sub>ID of glacier in the Randolph Glacier Inventory (RGI 7). Only for individual glacier submissions.</sub> |


---

### Optional variables (only for submissions with individual glacier output)

To allow further analyses of the optional submissions with individual glacier output, we encourage participants to provide data in addition to the mandatory variables listed above. 
See **Table 5** for more details. 

### Table 5. Output for individual glaciers (optional)

| <sub>Variable</sub> | <sub>Short name</sub> | <sub>Long name</sub> | <sub>Unit</sub> | <sub>Data type</sub> | <sub>Cell method</sub> | <sub>Temporal res.</sub> | <sub>Notes &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</sub> |
|---|---|---|---|---|---|---|:---|
| <sub>**Basin runoff**</sub> | <sub>`runoff_basin`</sub> | <sub>Runoff from the initial glacierized area</sub> | <sub>kg</sub> | <sub>float32</sub> | <sub>sum</sub> | <sub>monthly</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Glacier runoff, defined as melt minus refreezing plus liquid precipitation over the initial glacier area. The values represent “fixed-gauge” glacier runoff. Note, in contrast to the mandatory runoff above, this runoff here refers to the constant initial glacier area in year 2000 and thus includes rain and melt from the unglacierized area once the glacier has retreated. This variable may allow coupling the output to other large-scale hydrological models.</sub></details> |
| <sub>**Equilibrium line altitude**</sub> | <sub>`ELA`</sub> | <sub>Altitude of the annual equilibrium line</sub> | <sub>m above sea level</sub> | <sub>float32</sub> | <sub>maximum</sub> | <sub>annual</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Elevation of the annual equilibrium line, defined as the highest elevation over the course of the calendar year where the climatic mass balance is zero as derived from the mass-balance profile, i.e. the elevation where the profile intersects zero climatic mass balance.</sub></details> |
| <sub>**Transient equilibrium line altitude**</sub> | <sub>`snowline`</sub> | <sub>Altitude of the monthly equilibrium line</sub> | <sub>m above sea level</sub> | <sub>float32</sub> | <sub>maximum</sub> | <sub>monthly</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Elevation of the monthly equilibrium line, defined as the highest elevation over the course of a month, where the climatic mass balance is zero as derived from the mass-balance profile, i.e. the elevation where the profile intersects zero climatic mass balance. In case of sub-monthly model resolution, it is the maximum value during the month.</sub></details> |
| <sub>**Accumulation Area Ratio**</sub> | <sub>`AAR`</sub> | <sub>Annual Accumulation Area Ratio</sub> | <sub>—</sub> | <sub>float32</sub> | <sub>maximum</sub> | <sub>annual</sub> | <details><summary><sub>*Click to expand*</sub></summary><sub>Minimum ratio of accumulation area and total glacier area over the course of a year. The accumulation (ablation) area is the area where the annual mass balance is positive (negative).</sub> |


## Sign convention

In GlacierMIP4 all individual mass balance components are defined **positive**, including the mass loss terms melt and frontal ablation.

---

## File format and naming conventions

Separate files must be submitted for hindcast and the projection results, for annual and monthly variables and for each RGI region and climate scenario. All output must be provided as NetCDF files following GlacierMIP4 conventions.

(Entries in brackets [ ] need to be adjusted for each case. Note that the RGI number must be preceded by 0 when less than 10)

---

### Regional files for each RGI region (mandatory):

- One NetCDF file for the **annual** variables during the **hindcast** period 2000-2025  
  Naming convention: `[glaciermodel name]_rgi[number]_ERA5_annual.nc`  
  Example: `OGGM_rgi01_ERA5_annual.nc`

- One NetCDF file for the **monthly** variables during the **hindcast** period 2000-2025  
  Naming convention: `[glaciermodel name]_rgi[number]_ERA5_monthly.nc`  
  Example: `OGGM_rgi01_ERA5_monthly.nc`

- One NetCDF file for the **annual** variables for each **climate scenario** for the period 2025-2100/2300.  
  Naming convention: `[glaciermodel name]_rgi[number]_[GCM]_[SSP]_annual.nc`  
  Example: `OGGM_rgi01_MRI-ESM_ssp126_annual.nc`

- One NetCDF file for the **monthly** variables for each **climate scenario** for the period 2025-2100/2300.  
  Naming convention: `[glaciermodel name]_rgi[number]_[GCM]_[SSP]_monthly.nc`  
  Example: `OGGM_rgi01_MRI-ESM_ssp126_monthly.nc`

---

### Regional files with Individual-glacier output for each RGI region (optional):

Same as above: One NetCDF file for each combination of glacier model, RGI region, GCM and SSP. These dimensions are identified by the file name analogously to the convention for the mandatory files. **The individual glaciers are identified by the RGIId-Dimension in each region´s file.** To distinguish between regional and individual files, **“indiv”** must be added to the [region] in the file name:

- Example (annual variables): `OGGM_rgi01indiv_MRI-ESM_ssp126_annual.nc`  
- Example (monthly variables): `OGGM_rgi01indiv_MRI-ESM_ssp126_monthly.nc`

---

We will provide file structures, metadata conventions, and examples in the GlacierMIP4 `netcdf_templates` directory and NetCDF-format notebooks (work in progress - link to the Github will be provided soon). There, you will also find more information on the time axis and its intervals.

---

### How to submit:
⚠️**TBD**⚠️

---
---

<br><br><br>
---

## Contributors

The protocol was developed by (alphabetical order): Johannes Brunner, Johannes Fürst, Regine Hock, Matthias Huss, Ben Marzeion, Fabien Maussion, David Rounce, Lilian Schuster, Larissa van der Laan, Lander van Tricht, Ruitang Yang, Yeliz Yilmaz, Harry Zekollari.

---

## Contacts

- Regine Hock (regineho@uio.no)
- Harry Zekollari (harry.zekollari@vub.be)
- Johannes Brunner (johanmbr@uio.no)

---

## Authorship on GLACIERMIP4 publications

To become a co-author of the resulting publication you must fulfill the following three conditions (1-3): 

1) You must have made a substantial contribution to the manuscript through at least one of the following activities:

    a) data generation, i.e. you are a data provider. A data provider is defined as a person who performs all or part of the actual calculations of a model´s glacier projection data set that is used in the resulting publication. Others in the modeling research team may count as “data providers” if they have contributed to the projections in some other substantial capacity. For example, you have made significant intellectual contributions to the development of a new (yet unpublished) model or a variant of an existing model that is used here for the first time in the submitted projections, or you have created software used in this work, or contributed to data pre/post-processing or data quality control, or you have trained the person doing the calculations on how to use the model for this purpose.

    b) preparation, generation and curating of input datasets (e.g., GCM data)

    c) substantial contributions to the development of the GlacierMIP4 protocol

    d) substantial contributions to the conception, design and content of the paper

    e) data analyses of the submitted projections

    f) original drafting of the manuscript.

2) You must read drafts and provide meaningful feedback comparable to that of a peer reviewer prior to submission. Potential co-authors will be given at least two weeks advance notice to provide this feedback.

3) You must approve the submitted version prior to submission (and any substantially revised re-submitted versions). 

If you are a data provider but fail to fulfill requirements 2, you will be listed as data provider in the publication but not as co-author.

Note that advisors of any potential data contributors/co-authors or other group members/co-workers will only be included as a co-author if they also meet the criteria above. If you have questions, please contact both of the co-leads (Regine Hock and Harry Zekollari).

---

## To Be Added

The following items will be added to the protocol when finalized:

- Reference list at the end of the document
- Table 1 — Prescribed regional ice volumes for year 2000 (by RGI region)
- Table 2 — Final list of GCMs to be used for projections
- NetCDF templates and example notebooks for standardized output (`netcdf_templates/` and `notebooks/`)