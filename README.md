# Earth Observation Knowledge Packages
EOKP, as the governance object of the Earth Observation Knowledge Hub (EOKH), is designed for a specific knowledge landscape with organic coupling of domain knowledge, applications, relationships and processes. The EOKH is governed by the Knowledge Package, which is an organic coupling of knowledge, applications, relationships and processes for a specific knowledge field, and is used to present the various elements required in a complete application case in a structured way. This is an organic coupling of domain knowledge, applications, relationships and processes in a specific knowledge landscape, which is used to structurally present the various elements and relationships required in a complete application case. The knowledge in these packages is organised and provided by the knowledge producers, and includes most of the knowledge, resources and methods required to complete an application. These packages are organised and provided by the knowledge producers and contain most of the knowledge, resources and methodologies required to complete an application, enabling other researchers and practitioners to learn and use the knowledge at a low cost. This enables other researchers and domain practitioners to learn and reproduce the knowledge, resources and methodologies at low cost, and then use them in other similar application scenarios. application scenarios. This document shares the RDF file, which contains detailed metadata, and collates some of the knowledge packages for distribution at LOD, a list of which is available at https://github.com/cks1999/EOKP

Construction of Earth Observation Knowledge Hub based on Knowledge Graph，The knowledge package cases used in the article are url'd in http://cas.lod-cloud.net/, and the file
https://github.com/cks1999/ten-knowledge-package



# RDF in Lod-cloud
The RDF file contains the links and properties of the EOKP
  * [EOKP RDF github](https://github.com/cks1999/EOKP/EOKP.rdf)
  * [LOD](https://lod-cloud.net/)

# Table of knowledge in Lod-Cloud
Sample chart format for a single EOKP
![Figure 5  The knowledge graph of the EO application case of ‘Simulation of desertification dynamics in Ordos City from 2000 to 2030 with coupled natural-human factors’](https://github.com/cks1999/EOKP/assets/27915729/5d56f5b6-3c80-4709-9c05-5cabb976dc4e)

  * [Simulation of desertification dynamics in Erdos City from 2000 to 2030 with coupled natural-human factors](https://lod-cloud.net/dataset/SDDEC)
  * [Interpretation of Land Use Data in Ordos City](https://lod-cloud.net/dataset/ILUSOC)
  * [Soil & Water Assessment Tool](https://lod-cloud.net/dataset/SWAT)
  * [Atmospheric Correction of High Resolution Optical Images model](https://lod-cloud.net/dataset/model)
  * [Topography based Hydrological Model](https://lod-cloud.net/dataset/TOPMODEL)
  * [Geographically Weighted Regression Model](https://lod-cloud.net/dataset/GWR)
  * [High Accuracy Surface Modeling](https://lod-cloud.net/dataset/HASM)
  * [Distributed Hydrology Soil Vegetation Model](https://lod-cloud.net/dataset/DHSVM)
  * [Geographic detector model](https://lod-cloud.net/dataset/GeoDetector)
  * [Future land use simulation model](https://lod-cloud.net/dataset/FLUS)
  * [Parallel ice sheet model](https://lod-cloud.net/dataset/PISM)
  * [An automatic approach for land-change detection and land updates based on integrated NDVI timing analysis and the CVAPS method with GEE support](https://lod-cloud.net/dataset/model1)

# Related Links Lod-cloud
Addresses in the LOD-Cloud
* [Linked data](https://lod-cloud.net/)


# SPARQL endpoint

![Figure 9  SPARQL query terminal ](https://github.com/cks1999/EOKP/assets/27915729/e0ecf9cf-fefd-4785-a882-863b9ad15f2a)
![Figure 10  EOKP association relationship query demo](https://github.com/cks1999/EOKP/assets/27915729/f1ba1209-b2c7-414b-beb7-5ead2d658ff5)



# SPARQL demo

 ```python
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX iswc: <http://annotation.semanticweb.org/iswc/iswc.daml#>
PREFIX eokp: <http://eokh.org/eokp#>

SELECT ?case_title ?relation ?entity_name ?resource_url
WHERE {
  ?case a eokp:case ;eokp:title ?case_title .
  FILTER(REGEX(str(?case_title), "human factors", "i"))  # 'i' means case insensitive
  OPTIONAL { 
    ?case ?relation ?entity .
    ?entity eokp:title ?entity_name .
    ?entity eokp:resource_url ?resource_url .
  }# Get all the properties of the Case and their values
}
 ```
# Acknowledgement
Copyright by cks (caikuangsheng@126.com).
------
