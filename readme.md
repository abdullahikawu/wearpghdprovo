**A Semantic Framework for Wearable-Generated Patient Health Data**

_License_: 
_DOI_: 

**Overview**
The Wearable PGHD-PROVO Ontology is an extension of the PGHD-PROVO Ontology designed to model Patient-Generated Health Data (PGHD) collected from wearable devices (e.g., Fitbit, Withings). It provides:

Structured representation of activity, sleep, and vital signs data.

Provenance tracking (who collected data, when, and how).

Vendor-neutral mappings for interoperability (Fitbit, Withings, etc.).

Use Cases:
✔ Remote patient monitoring
✔ Clinical research aggregation
✔ IoT health data integration

**Quick Links**
Ontology Documentation ([Full specification])
SPARQL Endpoint (Query wearable PGHD data)
Example Data (Sample RDF datasets)
Cite This Work

**Ontology Structure** 
_Core Classes_
Class	Description
wearpghdprovo:DailyActivity	Steps, calories, MET-based activity levels
wearpghdprovo:Sleep	Sleep stages (REM, deep), efficiency, latency
wearpghdprovo:VitalSign	Heart rate, blood pressure, breathing rate
pghdprovo:PGHDRequest	Clinician’s request for wearable data

_Key Properties_
Property	Example
wearpghdprovo:steps	"8500" (steps/day)
wearpghdprovo:sleepEfficiency	"85" (percentage)
wearpghdprovo:heart_rate	"72" (bpm)
prov:wasGeneratedBy	Links data to a collection activity

**Getting Started**
1. Download the Ontology
bash
wget https://w3id.org/wearpghdprovo/wearpghdprovo-latest.ttl

**2. Query with SPARQL***
Example: "Get sleep data for Patient1"

Sparql
PREFIX wearpghdprovo: <https://w3id.org/wearpghdprovo#>  
SELECT ?sleep ?duration ?efficiency  
WHERE {  
  ?sleep a wearpghdprovo:Sleep ;  
         wearpghdprovo:sleepDuration ?duration ;  
         wearpghdprovo:sleepEfficiency ?efficiency ;  
         prov:wasAttributedTo <https://w3id.org/pghdprovo#Patient1> .  
}

**3. Extend with Custom Data**
turtle
@prefix wearpghdprovo: <https://w3id.org/wearpghdprovo#> .  
<#Sleep2> a wearpghdprovo:Sleep ;  
          wearpghdprovo:rem "90" ;  # REM duration in minutes  
          prov:wasDerivedFrom <#FitbitCharge5> .  

**License**
This ontology is licensed under CC BY 4.0.

**Citation**
If you use this ontology, please cite:

_bibtex_
@misc{wearpghdprovo2023,  
  author = {Kawu, Abdullahi Abubakar},  
  title = {Wearable PGHD-PROVO Ontology},  
  year = {2023},  
  publisher = {GitHub},  
  url = {https://github.com/abdullahikawu/wearpghdprovo}  
}

**Contributing**
Report issues on GitHub.

Submit PRs for any observation: property mappings (e.g., Apple Health, Garmin).

**Maintainer**: Abdullahi Abubakar Kawu (@abdullahikawu)
