# knowledge-package
Construction of Earth Observation Knowledge Hub based on Knowledge Graph，The knowledge package cases used in the article are url'd in http://cas.lod-cloud.net/, and the file
https://github.com/cks1999/ten-knowledge-package



# RDF in Lod-cloud

  * [EOKP RDF](https://lod-cloud.net/dataset/SWAT)

# Table of knowledge in Lod-Cloud
![image](https://github.com/cks1999/EOKP/assets/27915729/e2962303-cf20-4c2c-a2cf-2beab47a7696)


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
* [Linked data](https://lod-cloud.net/)


# SPARQL endpoint

![image](https://github.com/cks1999/EOKP/assets/27915729/8a0bb49d-9bba-4e4a-9192-9eed0e93ed42)

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
