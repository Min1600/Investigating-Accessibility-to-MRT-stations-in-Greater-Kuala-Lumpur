# Investigating-Accessibility-to-MRT-stations-in-Greater-Kuala-Lumpur


### **_Introduction_**

The first and last mile (FLM) problem is a crucial factor in underutilization of public transportation, it is the difficulty in accessing public transit stations (Lu, et al., 2024). FLM problem increases the likelihood of private car usage to access public transit stations which contributes to traffic congestion, air pollution and increases expenditure on construction and maintenance of parking facilities around stations (Lu et.al, 2024). The systematic review stated that type of public transport available and the spatial accessibility of public-transport stops are some of the factors that affect FLM mode choice.

MRT and LRT services in Greater Kuala Lumpur (GKL) provide efficient and reliable services to the population. However, despite that Malaysia’s urban transport challenges are longstanding and expanding rail infrastructure alone would be insufficient if travellers did not shift away from private vehicles (Almselati et al., 2011; Chuen et al., 2014). A more recent qualitative study of 34 riders in urban and suburban GKL found that commuters continued to encounter first-mile barriers, including long walking distances and dependence on private vehicles or informal alternatives to reach rail stations (Shukri, 2025; Khairi & Ho, 2025). Chin et al. (2025) documented that 46% of Putrajaya residents are using e-hailing and DRT services. Nearly 3 million vehicles on Klang Valley roads daily results in traffic congestion, increased travel times and negative impacts on the environment and economy (Yusoff et al., 2021). The Malaysian Government aims to increase public transport usage to approximately 40% by 2030 (Halim, et al., 2025). This motivates investigations in improvements of pedestrian connections, feeder buses and demand-responsive transport (DRT).

This project aims to develop a spatial decision-support framework for identifying and prioritising FLM interventions around MRT stations in GKL. This framework is created by combining (all public data), population estimates from WorldPop, pedestrian-network measurement derived from OpenStreetMap and using OSMnx python library for geospatial calculations, MRT service data, existing DRT coverage and station ridership from Official Malaysia Open Data Portal (data.gov.my) GTFS. Using this data-driven framework to identify areas with indirect walking routes, excessive walking distances or insufficient connecting services. These accessibility profiles will support provisional recommendations for pedestrian infrastructure, feeder bus service or DRT service improvements.

### **_Related Work_**

LRT station usage can be determined by the walkability to the station, a higher walkability index leads to increase in pedestrians in LRT stations (Chin et al., 2020). Ruslan et al. (2023) found that walkability varied spatially, with lower accessibility along some primary roads in Kuala Lumpur. Khoo (2025) examined walkability in GKL using road permeability and POI accessibility. All these studies found that walkability is multidimensional and that spatial indicators alone cannot capture factors such as safety, comfort, dedicated pedestrian facilities and weather protection. This project will not attempt to measure walkability, instead it isolates pedestrian-network accessibility by measuring network walking distance and route circuity.

Chin et al. (2020) documented actual walking distances of 2,500 m and 2,300 m between the Sri Rampai and Miharja LRT stations and nearby residential areas. A route between Miharja and the Chan Sow Lin commercial area was even longer, at 3,400 m. These destinations were only approximately 398 - 543 m from the stations by straight-line distance. However, the study only examined three stations and demonstrated connectivity using small number of routes. This project addresses the gap by attempting to calculate the circuity around all MRT stations. Distance, circuity, population and public transport data can be calculated consistently across a large number of catchment areas, allowing the problem to be examined at a larger spatial scale. The results should therefore be interpreted as a screening of pedestrian-network accessibility barriers rather than a complete assessment of the pedestrian experience.

Rahaman et al. (2025) developed a GIS-based Transit Accessibility Index for Puncak Alam by integrating job density, land use, travel time, public-transport service and demographic data. The model classified areas according to their overall accessibility and was presented as a decision-support tool that could inform the allocation of feeder services, DRT and other transport improvements. However, their pilot focused on general accessibility within a suburban area without direct rail connectivity, and its planned GTFS integration was not implemented. The present project applies a related decision-support objective using differing data and specifically evaluates residential areas within the catchment of existing MRT stations.

Existing GKL studies generally examine walkability at a small number of stations or construct broad accessibility indices. This project instead conducts a consistent network-based assessment across all MRT station catchments and links obtainable spatial and administrative data to specific intervention categories. This can make the framework reproducible, scalable and capable of being updated as transport conditions change.

### **_Business Model_**

This project represents information-based brokering because it integrates multiple spatial and transport datasets to produce value-added accessibility profiles and decision-support information for transport planners. It helps decision-makers identify areas where pedestrian infrastructure, feeder-bus or DRT interventions may warrant further investigation. The project would be a business-to-government or business-to-business analytical service.

The project implements descriptive analysis to summarise existing FLM conditions and apply clustering algorithms using unsupervised machine learning to group residential areas into accessibility profiles. The prescriptive component will use transparent decision rules to match each accessibility profile with a suitable intervention.

This project can benefit transport operators as it provides evidence for identifying where existing feeder routes or DRT may have insufficient coverage or frequency. For infrastructure planners, the project identifies communities that require improvements in pedestrian infrastructure, connecting paths or additional station entrances. Financially, the project can help decision-makers allocate limited budgets more efficiently. This reduces the risk of implementing expensive services in unsuitable locations.

The principal direct users are expected to be Prasarana, Rapid Bus and local authorities because they control different components of first-mile accessibility. Rapid Bus manages feeder and On-Demand operations, while local authorities are generally responsible for surrounding pedestrian infrastructure. The decision-support system allows these stakeholders to coordinate interventions using a common evidence base.



<div align="center">This text is centered.</div>

Almselati, A. S. I., Rahmat, R. A. O. K., & Jaafar, O. (2011). An overview of urban transport in Malaysia. _Social Sci, 6_(1), 24–33.

Chin, S. J. Y., Goh, B. H., Teo, F. Y., Kang, B. G., & Yuen, C. W. (2020). Pedestrian walkability index for light rail transit (LRT) stations in Klang Valley, Malaysia. In F. M. Nazri (Ed.), _Proceedings of AICCE'19: Transforming the nation for a sustainable tomorrow_ (pp. 737–748). Springer. [https://doi.org/10.1007/978-3-030-32816-0_52](https://doi.org/10.1007/978-3-030-32816-0_52)

Chiu Chuen, O., Karim, M. R., & Yusoff, S. (2014). Mode choice between private and public transport in Klang Valley, Malaysia. _The Scientific World Journal, 2014_(1), 394587. [https://doi.org/10.1155/2014/394587](https://doi.org/10.1155/2014/394587)

Gregory Ho, W. S., Shukri Mohamed Khairi, & Ling, K. S. S. (2025). _Closing the first-and-last mile gap in Greater Kuala Lumpur_. Khazanah Research Institute.

Halim, M. A., Rosni, N. A., & Tsong, T. B. (2025). Preliminary insights into feeder bus usage: A case study of Asia Jaya LRT station in the Klang Valley. _Journal of Design and Built Environment_, 74–88.

Khoo, W. Y. (2025). _Measuring walkability of Greater Kuala Lumpur_. Khazanah Research Institute.

Lu, Y., Kimpton, A., Prato, C. G., Sipe, N., & Corcoran, J. (2024). First and last mile travel mode choice: A systematic review of the empirical literature. _International Journal of Sustainable Transportation, 18_(1), 1–14. [https://doi.org/10.1080/15568318.2023.2243517](https://doi.org/10.1080/15568318.2023.2243517)

Rahaman, L. A., Naharudin, N., Salleh, S. A., & Alias, E. (2025). A multi-criteria GIS approach to evaluate transit accessibility index: Integrating FAHP in suburban Malaysia. _The International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences, 48_, 255–263. [https://doi.org/10.5194/isprs-archives-XLVIII-4-W6-2025-255-2025](https://doi.org/10.5194/isprs-archives-XLVIII-4-W6-2025-255-2025)

Ruslan, N., Naharudin, N., Salleh, A. H., Halim, M. A., & Abd Latif, Z. (2023). Spatial walkability index (SWI) of pedestrian access to rail transit station in Kuala Lumpur city center. _Planning Malaysia, 21_. [https://doi.org/10.21837/pm.v21i24.1268](https://doi.org/10.21837/pm.v21i24.1268)

Shukri Mohamed Khairi, & Gregory Ho, W. S. (2025). _Greater Kuala Lumpur's public transportation and its viability: A qualitative study_. Khazanah Research Institute.

Yusoff, I., Ng, B.-K., & Azizan, S. A. (2021). Towards sustainable transport policy framework: A rail-based transit system in Klang Valley, Malaysia. _PLOS ONE, 16_(3), e0248519. [https://doi.org/10.1371/journal.pone.0248519](https://doi.org/10.1371/journal.pone.0248519)

