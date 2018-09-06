# Turkey-Vector-Maps
Area, centroid and population weighted vector maps of Turkey in IBBS4 to IBBS1 detail.

![IBBS4 Population Weighted Map](/PopulationWeighted/PNG/IBBS4.png?raw=true "IBBS4 Population Weighted Map")
    
*(Quick note for those of you who want to map the 2018 elections: this set is missing two IBBS4 entities that were incorporated in August 2017. The Aksaray district has a new subdistrict which used to be a "belde" within the Merkez subdistrict before: Sultanhanı. The "belde" of Kemalpaşa that used to be a part of Artvin district's Hopa subdistrict also became a subdistrict. So if you are perfectionist, either get your GIS program out and carve these out--and please update this git if you do so, or add the results for these subsdistricts together in your data set. If you are not a perfectionist, the difference is really small, so you can basically ignore these:)*

The project has three directories:
- Area: contains regular maps.
- Centroid: contains centroids of geographical entities.
- PopulationWeighted: contains population weighted maps.
In each directory, the data is available in Shapefile, GeoJSON and PNG format.
Each directory contains 5 or 6 files:
- IBBS4: This is the district level (İlçe in Turkish)
- IBBS3_Election_Distrcits: These are the electoral districts. Almost identical to IBBS3 with the exception of multiple electoral districts in Istanbul, Ankara and Izmir.
- IBBS3: Districts (İl in Turkish)
- IBBS2: These are the sub statistical units. They are widely used by Turkish Statistical Institute: http://www.turkstat.gov.tr/.
- IBBS1: These are the top level statistical units. Also used by Turkish Statistical Institute.
- TR: The whole country

Area maps were initially based on a couple of different sources. I simplified the geometries quite a lot and even divided some IBBS4 districts by hand.
Centroids were simply done by using QGIS.
Weighted Population Maps were initially done with ScapeToad (https://scapetoad.choros.ch/) for all levels separately and hand cleaned.

All files contain a lot of namespace. For each level above (including the level of the current file) there are four names:
- The Turkish Name
- The Short Turkish Name
- The ASCII Name
- The Short ASCII Name

IBBS3 level also contains license plate numbers that are used often in Turkey for matching data.
The files also contain total, urban and rural populations for 2017. These were used to do the reshaping for population weighted maps.

Population weighted maps are not perfect representations. That is, Each population weighted polygon is not exactly proportional to its population (yeah, maps are hard that way:). So each entry includes an error value. Values close to 100 are better. Values over 100 mean that the polygon is actually larger than its exact representation. For example, an error value of 120 means that the polygon should be reduced by 20% to be exactly proportional to its population. 
