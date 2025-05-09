# Pack Name
----

**Pack Name:Cribl Stream: TripPop web apps & services 011y pipelines**

**Account ID: TripPop**

**Company: NotaRealco**

**Subsidiary: Trip-Pop**

**Team: Web Apps & Services**

**Purpose: Ingest data from web apps & services infrastructure**
 

# Requirements Section
---

Before you begin, ensure that you have met the following requirements:

* You are using Stream version 4.12 or greater (Cloud managed worker groups will already meet this requirement)
* You are using the approved corporate git repo
* You have logged Stream Leader & Worker IPs in our IP based ACL to ensure that your workers and leaders can access the repo
* You have identified all globally distributed worker groups to be used for ingesting data

# Release Notes
---

## v0.0.1: Alpha deployment which includes
 
### **SOURCES:**
**Cribl HTTP for Edge Nodes**

### **DESTINATIONS**
**Cribl Lake datasets:** TripPop-Websrv-Logs; TripPop-Websrv-Metrics; TripPop-Webapp-Logs; TripPop-Webapp-Metrics

### **SOURCE DATA TYPES**
Reverse proxy Nginx logs (custom json)
Reverse proxy Nginx error logs (default)
Linux System Metrics (from Cribl Edge) 

### **DESTINATION DATA TYPES**
Parsed ndjson for Lake & Lakehouse with _raw unmodified

### **TRANSFORMATIONS** 
**Preprocessing:**
 - Lookup table enrichment to add dataset & device characteristics
 - Eval to extract Cribl Fleet from internal fields; and then datacenter value by splitting the Fleet name 
 - Aggregation to create statistics

**Nginx access logs (custom json):**
 - Parsing of _raw to fields
 - Client network identification & enrichment
 - Client network geo-enrichment
 - Creating / validating accelerated fields for Lake & Lakehouse

**Nginx error logs (default):**
 - Parsing of _raw to fields
 - Client network identification & enrichment
 - Client network geo-enrichment
 - Creating / validating accelerated fields for Lake & Lakehouse

# Contributing to the Pack
---
Blame JR


## Contact
---
To contact us please email dataengineering@notarealco.com


## License
---
**NotaRealco ConfidentialSoftwareData License v2025**
