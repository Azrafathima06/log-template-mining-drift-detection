# System Architecture

## High-Level Flow

1. Log Ingestion  
   - Accepts .log, .txt, or .json files  
   - Supports time-window filtering  

2. Preprocessing  
   - Timestamp extraction  
   - Severity parsing  
   - Template normalization  

3. Template Mining  
   - Log lines grouped into templates  
   - Dynamic fields replaced with wildcards (*)  
   - Template frequency calculated  

4. Drift & Spike Detection  
   - Baseline window vs Current window comparison  
   - New template detection  
   - Frequency spike detection  

5. JSON Output Generation  
   - Structured template data  
   - Aggregated counts  
   - Drift flags  

6. UI Integration  
   - Template ranking  
   - Severity distribution  
   - Drift alerts panel
