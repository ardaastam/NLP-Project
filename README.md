#  Socioeconomic Status Inference from Social Media

This repository presents an NLP-based pipeline for estimating the socioeconomic status (SES) of social media users through occupation inference from their self-written profile descriptions.



##  Project Overview

Millions of users publish their bios on social media without structured occupational or demographic information. We aim to infer:
- Occupation (via keyword matching)
- ISEI socioeconomic score (1–100)
- SES class (Low / Middle / High)
- Country (from fuzzy location matching)



##  Methodology

1. **Regex + Keyword Matching**  
   - English & Turkish occupation terms  
   - Hierarchical dictionaries (category → job title → keywords)

2. **ISEI Score Assignment**  
   - Based on Ganzeboom et al. (1992)  
   - Extended for modern jobs (e.g., Data Scientist, Blockchain Expert)

3. **SES Classification**  
   - High SES: ISEI ≥ 75  
   - Middle SES: 65 ≤ ISEI < 75  
   - Low SES: ISEI < 65

4. **Country Detection**  
   - Handles free-text city/region names like “Kartal”, “Istanbul/Çengelköy”  
   - Uses city-to-country dictionaries & fuzzy logic



##  Project Structure

```
├── data/                   # Input and enriched user data
├── scripts/                # Python scripts for processing
├── notebooks/              # Jupyter notebooks for exploration
├── outputs/                # WordClouds, plots, TF-IDF, maps
├── README.md
└── requirements.txt
```



##  Installation

```bash
pip install -r requirements.txt
pandas
numpy
matplotlib
wordcloud
plotly
pycountry
```


##  Example Usage

```bash
python scripts/occupation_matcher.py
python scripts/isei_mapper.py
python scripts/ses_classifier.py
```



##  Outputs

-  Choropleth maps of SES distribution  
-  TF-IDF & WordClouds per SES class  
-  Occupation–ISEI summaries  
-  CSV of all users with inferred SES



##  References

- Ganzeboom, H. B. G., et al. (1992). *ISEI of Occupational Status*  
- ISCO-08 occupational classification  
- Chiticariu et al. (2010). *Rule-based IE Systems*  
- Ratner et al. (2017). *Snorkel: Weak Supervision*  
- Çöltekin, Ç. (2010). *Turkish Morphological Analyzer*



##  Author

This project was developed as part of an NLP university course project from Arda Astam.
