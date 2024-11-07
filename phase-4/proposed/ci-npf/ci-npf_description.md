# AeroCom Experiment: Climate Impact of NPF versus Growth in Climate Models (CI-NPF)

**Organizers:**
- Sara Blichner ([sara.blichner@aces.su.se](mailto:sara.blichner@aces.su.se))
- Ilona Riipinen ([ilona.riipinen@aces.su.se](mailto:ilona.riipinen@aces.su.se))
- Anouck Chassaing ([Anouck.Chassaing@aces.su.se](mailto:Anouck.Chassaing@aces.su.se))
- Hamish Gordon ([hamishg@andrew.cmu.edu](mailto:hamishg@andrew.cmu.edu))
- Xu-Cheng He ([xh346@cam.ac.uk](mailto:xh346@cam.ac.uk))

**Timeline:**
- **Plan open for discussion:** until 1 February 2025
- **Deadlines for submission of model data:**
    - Tier I experiments: 1 May 2025
    - Tier II experiments: 30 June 2025

## Motivation
Estimates of the contribution of NPF to CCN are primarily model-derived and vary widely ([Stolzenburg et al., 2023](https://doi.org/10.1103/RevModPhys.95.045002)). Recent studies show large variability in NPF's contribution to N100/CCN. Some suggest that increased nucleation reduces N100/CCN ([Blichner et al., 2021](https://doi.org/10.5194/acp-21-17243-2021); [Patoulias et al., 2024](https://doi.org/10.1029/2023GL106182); [Roldin et al., 2019](https://doi.org/10.1038/s41467-019-12338-8); [Sullivan et al., 2018](https://doi.org/10.1038/s41612-018-0019-7)), while others show an increase ([Gordon et al., 2017](https://doi.org/10.1002/2017JD026844); [Svenhag et al., 2024](https://doi.org/10.5194/gmd-17-4923-2024)). Stolzenburg et al. (2023) suggest that models with more SOA show a larger NPF impact, which may be constrained by observations.

## Objectives
- Investigate model sensitivity to increased NPF versus added condensate to understand the varying impacts on cloud dimming and brightening.
- Constrain/evaluate size distribution dynamics to reject models with unrealistic NPF impacts on the CCN budget.
- Classify models as growth limited or formation rate limited.
- Determine the impact of NPF on ERFaci in models with different NPF sensitivities.

## Proposed Model Experiments

### All Simulations
- **Year:** 2014 (with a 3-month spin-up starting from 2013-10-01 or earlier)
- **Nudging:** Horizontal winds (or vorticity and divergence) and pressure towards ERA-Interim, not temperature.
- **SST:** Prescribed from reanalysis/observed data.
- **Baseline:** Follow CMIP6 AerChemMIP histSST runs.

### Tier 1 Simulations
| Simulation Name | Multiply Nucleation Rate by | Multiply Condensable Vapors by | Multiply Vapors in Early Growth by | Anthropogenic Emissions | Purpose |
|-----------------|-----------------------------|--------------------------------|------------------------------------|--------------------------|---------|
| CTRL            | 1                           | 1                              | 1                                  | PD                       | Control simulation |
| Jx0             | 0                           | 1                              | 1                                  | PD                       | Evaluate CCN from NPF |
| Jx10            | 10                          | 1                              | 1                                  | PD                       | Evaluate sensitivity to nucleation rate |
| Cx2             | 1                           | 2                              | 1                                  | PD                       | Evaluate sensitivity to condensing mass |
| Jx10Cx2         | 10                          | 2                              | 1                                  | PD                       | Evaluate joint sensitivity |
| GRx5            | 1                           | 1                              | 10                                 | PD                       | Evaluate sensitivity to early growth |

*Output should include double radiation call for CRE and DRE quantification.*

### Tier 2 Simulations
| Simulation Name | Multiply Nucleation Rate by | Multiply Condensable Vapors by | Multiply Vapors in Early Growth by | Anthropogenic Emissions | Purpose |
|-----------------|-----------------------------|--------------------------------|------------------------------------|--------------------------|---------|
| CTRL_PI         | 1                           | 1                              | 1                                  | PI                       | Control simulation |
| Jx0_PI          | 0                           | 1                              | 1                                  | PI                       | Evaluate CCN from NPF |

## Model Output Variables
Refer to [Model_output_CI-NPF](#) and AeroCom diagnostics CTRL+X 2018/2019 for variable details.

### Model Output Submission
- Follow AeroCom III-DURF output specifications.
- Submit data to the [AeroCom website](https://aerocom.met.no/FAQ/data_access/submit_data).

### File Naming Convention
Format: `aerocom3_<ModelName>_CI-NPF-<SimulationName>_<VariableName>_<VerticalCoordinateType>_<Year>_monthly.nc`

Examples:
- 2-D: `aerocom3_GEOS-i33p2_CI-NPF-histSST_ps_Surface_2008_monthly.nc`
- 3-D: `aerocom3_GEOS-i33p2_CI-NPF-histSST-oa_ModelLevel_2009_monthly.nc`

## References
- Blichner, S. M., et al., (2021). *Reduced effective radiative forcing from cloud–aerosol interactions...* Atmos. Chem. Phys., 21, 17243–17265. [DOI](https://doi.org/10.5194/acp-21-17243-2021)
- Gordon, H., et al., (2017). *Causes and importance of new particle formation...* J. Geophys. Res. Atmospheres, 122, 8739–8760. [DOI](https://doi.org/10.1002/2017JD026844)
- Stolzenburg, D., et al., (2023). *Atmospheric nanoparticle growth.* Rev. Mod. Phys., 95, 045002. [DOI](https://doi.org/10.1103/RevModPhys.95.045002)
- [Additional references are listed above]
