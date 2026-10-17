# Haryana UrbanGeoAI Explorer

## A Rule-Based GIS Chatbot for Urban Expansion and Land-Cover Analysis (2017–2025)

### Project Overview

Haryana UrbanGeoAI Explorer is a Google Earth Engine application prototype designed to support conversational interaction with satellite-derived land-cover information.

The project integrates Dynamic World V1 land-cover classifications, spatial analysis, and a rule-based chatbot interface developed using the Google Earth Engine JavaScript API.

### Study Area

Haryana, India

### Study Period

2017 and 2025

### Technologies

- Google Earth Engine JavaScript API
- Google Earth Engine UI widgets
- Dynamic World V1
- FAO GAUL 2015 administrative boundaries
- GitHub for source code and documentation

### Objectives

1. Generate comparable land-cover maps for 2017 and 2025.
2. Visualize built-up surfaces across Haryana.
3. Calculate exploratory built-up area statistics.
4. Develop a chatbot-style interface for supported GIS questions.
5. Display maps, numerical responses, and land-cover charts.
6. Document analytical methods and limitations.

### Application Features

- Interactive Haryana land-cover map
- 2017 and 2025 layer visualization
- Built-up area display
- Exploratory built-up change calculations
- Land-cover comparison chart
- Rule-based question recognition
- Unsupported-question fallback
- Land-cover legend and methodology notes

### Methodology

Dynamic World annual modal composites were prepared for 2017 and 2025. The most frequently predicted land-cover class was selected for each pixel.

Built-up surfaces were identified using Dynamic World class 6. Area calculations were performed using pixel-area summation at an exploratory 100-meter analysis scale.

The chatbot uses predefined keyword rules to select GIS operations and display corresponding responses.

### Limitations

- The chatbot is rule-based, not a generative AI model.
- It does not independently interpret raw satellite imagery.
- Land-cover predictions are subject to classification uncertainty.
- Seasonal differences and unequal observation counts may affect comparisons.
- The initial area calculations use a generalized 100-meter analysis scale.
- Reported area changes are exploratory and have not been independently validated.
- The prototype does not yet support arbitrary district-level questions.

### Project Status

Prototype implementation and testing. Final deployment URL and verified results will be added after successful testing.

### Author

Harsh Vashishth

GIS and Remote Sensing Portfolio:  
https://harshvashishth-gis-developer.github.io/

GitHub:  
https://github.com/harshvashishth-gis-developer
