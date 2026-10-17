Haryana UrbanGeoAI Explorer
Rule-Based GIS Chatbot for Land-Cover and Urban Expansion Analysis (2017–2025)
Launch the Google Earth Engine App
Project Overview
Haryana UrbanGeoAI Explorer is an interactive, rule-based GIS chatbot prototype built with the Google Earth Engine JavaScript API. It helps users explore satellite-derived land-cover patterns in Haryana, India, compare 2017 and 2025, and request exploratory built-up area statistics through a question-driven interface.
The chatbot recognizes a predefined set of question types. It is not a generative AI chatbot or a vision-language model, and it does not interpret raw satellite images independently.
Study Area and Data
Item	Details
Study area	Haryana, India
Comparison years	2017 and 2025
Land-cover source	Google Dynamic World V1 (GOOGLE/DYNAMICWORLD/V1)
Input imagery	Sentinel-2-derived land-cover predictions
Native dataset resolution	10 m
Boundary	FAO GAUL 2015 Level 1 (FAO/GAUL/2015/level1)
Prototype area calculation scale	100 m (exploratory)
Platform	Google Earth Engine JavaScript API and Earth Engine Apps


Dynamic World provides nine land-cover classes: water, trees, grass, flooded vegetation, crops, shrub and scrub, built, bare, and snow and ice.
Features
- Display annual modal land-cover maps for 2017 and 2025.
- Highlight areas classified as built-up in the 2025 composite.
- Calculate approximate built-up areas for each comparison year and their net difference.
- Visualize pixels that changed from non-built in 2017 to built in 2025 as potential new built-up classifications.
- Display a comparative chart of the nine land-cover class areas.
- Answer predefined questions using keyword-based intent recognition.
- Explain map classes and provide a fallback response for unsupported questions.
Example Chatbot Questions
Example question	Prototype response
Show land cover in 2017	Displays the 2017 land-cover map
Show land cover in 2025	Displays the 2025 land-cover map
Show built-up areas in 2025	Highlights mapped built-up pixels
How much did built-up area change?	Computes approximate areas and net change; displays potential new built-up pixels
Show land-cover statistics	Displays the land-cover class-area comparison chart
Explain the map	Describes the dataset, classes, and limitations
What is the weather tomorrow?	Returns an unsupported-question message


Methodology
1. Boundary selection: Filter the FAO GAUL Level 1 collection to Haryana, India.
2. Annual compositing: Filter Dynamic World observations to each calendar year and calculate the modal (label) class at each pixel.
3. Built-up identification: Select pixels assigned Dynamic World class 6 (built).
4. Area estimation: Sum ee.Image.pixelArea() over mapped classes and convert square meters to square kilometers. The prototype uses a 100 m reduction scale for manageable statewide exploration.
5. Change comparison: Subtract 2017 built-up area from 2025 built-up area to estimate net mapped change. Separately, flag pixels labeled non-built in 2017 and built in 2025 as potential new built-up classifications.
6. Chatbot interface: Use Earth Engine ui.Textbox, ui.Select, ui.Button, ui.Panel, ui.Map, and ui.Chart widgets to connect supported text intents to maps, calculations, and explanations.
7. Client/server interaction: Use Earth Engine server-side computations and asynchronous evaluate() callbacks to display numeric results in the client-side UI.
Architecture
User question / example selection
               |
               v
Client-side keyword intent recognition
               |
      +--------+---------+
      |                  |
      v                  v
Map / legend action   Earth Engine analysis
      |                  |
      |                  v
      |             Area / chart result
      |                  |
      +--------+---------+
               |
               v
Updated map + chatbot response panel
Project Screenshots
1. Interactive GIS Chatbot (Final Prototype)

The final Google Earth Engine UI with question input, response panel, legend, and interactive Haryana land-cover map.
2. Annual Land-Cover Comparison: 2017 vs 2025

Annual modal Dynamic World composites, visualized side by side using a consistent class palette.
3. Class-Wise Land-Cover Area Chart

Exploratory class-area comparison in square kilometers. The chart reflects the script's analysis settings; estimates are not independently validated.
4. Haryana Administrative Boundary

5. Dynamic World 2017: Seasonal Inspection

6. Dynamic World 2025: Seasonal Inspection

The Day 2 inspection maps use January–March observations, while the later annual comparison uses January–December observations.
7. Built-Up Class Preview (2025)

8. Earth Engine Dataset Inspection

Console checks of the study boundary, image availability, and data filtering.
Repository Structure
haryana-urbangeoai-explorer/
├── README.md
└── screenshots/
    ├── finalday_chatbot.png
    ├── Day3_Haryana_LandCover_2017_vs_2025.png
    ├── Haryana_Landcover.png
    ├── Day2_Haryana_Boundary.png
    ├── Day2_DynamicWorld_2017.png
    ├── Day2_DynamicWorld_2025.png
    ├── Day2_BuiltUp_2025.png
    └── Day2_Console_Inspection.png
Add your saved, verified Earth Engine JavaScript source in a gee-scripts/ folder when ready. Source code is not included in this screenshot package.
Limitations and Interpretation
- Rule-based interface: Only supported keyword patterns are recognized; arbitrary natural-language questions and district-specific analyses are not implemented.
- Classification uncertainty: Dynamic World labels are predictions, not verified ground truth. Built-up surfaces can be confused with bare land and other classes.
- Temporal sensitivity: Annual modal composites may be influenced by seasonality, uneven observation counts, and data gaps.
- Confidence filtering: The baseline prototype does not apply a probability threshold.
- Exploratory area estimates: Area calculations at 100 m do not constitute validated native-resolution land-cover area estimates.
- Change interpretation: Pixels switching to the built class are candidate changes, not confirmed construction. Net area change and gross newly classified built pixels are different measures.
- Boundary vintage: The FAO GAUL boundary is from 2015; check licensing and administrative consistency before public redistribution or more detailed district analysis.
Run the Project
1. Open the live Earth Engine App.
2. Choose a sample question or enter a supported question in the textbox.
3. Click Ask GIS Chatbot.
4. View the updated map, text response, or chart. Large area calculations may take time.
To reproduce or modify the application, open the .js source in the Earth Engine Code Editor using an Earth Engine-enabled account and project. Verify data access and App publishing permissions.
Learning Outcomes
- Building reusable Dynamic World annual land-cover composites.
- Calculating class-wise area statistics with pixel-area and region reducers.
- Understanding seasonality, classification confidence, and change-detection limitations.
- Designing rule-based geographic question intents.
- Building interactive applications with Earth Engine UI widgets.
- Connecting client-side interfaces to server-side geospatial calculations.
References
- Dynamic World V1 dataset catalog
- Introduction to Dynamic World — Part 1
- Introduction to Dynamic World — Part 2
- Introduction to Dynamic World — Part 3
- Earth Engine UI overview
- FAO GAUL 2015 Level 1 catalog
Author
Harsh Vashishth
GIS Portfolio · GitHub Profile
Project period: October 12–17, 2026
