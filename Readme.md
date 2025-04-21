---
---
---

# Proposal for Semester Project

```{=html}
<!-- 
Please render a pdf version of this Markdown document with the command below (in your bash terminal) and push this file to Github. Please do not Rename this file (Readme.md has a special meaning on GitHub).

quarto render Readme.md --to pdf
-->
```

**Patterns & Trends in Environmental Data / Computational Movement Analysis Geo 880**

| Semester: | FS25 |
|:-------------------------|:---------------------------------------------|
| **Data:** | GPS data of seed dispersing spotted nutcrackers (Nucifraga caryocatactes) |
| **Title:** | The title of your project |
| **Student 1:** | Simon Behringer |
| **Student 2:** | Marius King |

## Abstract

<!-- (50-60 words) -->

Nutcrackers (*Nucifraga caryocatactes*) play a crucial role in forest regeneration by dispersing seeds. Analyzing their movement data allows us to identify frequently revisited sites, which can provide insights into harvesting and caching behavior as well as dispersal distances. Understanding these movement patterns and their ecological implications is essential for forest conservation and management.

## Research Questions

1.  How do frequently revisited sites vary among individuals, and can distinct clusters of these sites be identified?
2.  Are there significant differences in movement patterns between individuals, considering factors such as sex?

<!-- (50-60 words) -->

## Results / products

<!-- (50-100 words) -->

<!-- What do you expect, anticipate? -->

We aim to produce:

-   A visualization of individual movement patterns highlighting frequently revisited sites and potential clusters.
-   A boxplot comparing movement pattern similarities between males and females.

We expect that individuals will exhibit distinct movement patterns and revisited sites. Differences between males and females may emerge, with males potentially covering greater distances in search of breeding sites, while females may focus more on specific food resources. Males may prioritize caching sites, whereas females might spend more time at harvesting locations.

## Data

<!-- (100-150 words) -->

<!-- What data will you use? Will you require additional context data? Where do you get this data from? Do you already have all the data? -->

We will analyze GPS data from 31 seed-dispersing spotted nutcrackers tracked in the Davos region of the Swiss Alps. Most birds were monitored between early August and late September, with some individuals tracked year-round. GPS sampling frequency varies throughout the year and is highest during the seed harvesting and caching season (August–September), with locations recorded every 15 minutes from 10:00 to 20:00.

Since our focus is on movement patterns, we will not incorporate additional context data.

**Data source:**\
Graf V, Sorensen MC, Mueller T, Neuschulz EL. 2024. Data from: *Study “Movement patterns of seed dispersing spotted nutcrackers (Nucifraga caryocatactes)”*. Movebank Data Repository. <https://doi.org/10.5441/001/1.324>

## Analytical concepts

<!-- (100-200 words) -->

<!-- Which analytical concepts will you use? What conceptual movement spaces and respective modelling approaches of trajectories will you be using? What additional spatial analysis methods will you be using? -->

We will:

1.  Filter individuals suitable for movement analysis and extract subtrajectories following Laube & Purves (2011).
2.  Compute movement similarity using different measures (DTW, EDR, LCSS, FD) and compare individuals and sexes using ANOVA.
3.  Identify frequently revisited sites. Due to the lack of field observations, we will not distinguish between harvesting and caching sites.

## R concepts

<!-- (50-100 words) -->

<!-- Which R concepts, functions, packages will you mainly use. What additional spatial analysis methods will you be using? -->

For data processing and visualization, we will use the following R packages:\
- **Data handling & visualization:** `tidyr`, `readr`, `dplyr`, `sf`, `ggplot2`\
- **Movement similarity analysis:** `SimilarityMeasures`, analyzed via `aov`\
- **Revisited site analysis:** `recurse` to identify revisited sites, visit duration, and return intervals\
- **Clustering:** We will determine a threshold for frequently revisited sites by plotting revisit density and selecting the minimum density separating rare from frequent revisits. Clustering will be performed, and the size of revisited sites will be estimated using 95% convex polygons (`adehabitatHR`).

## Risk analysis

<!-- (100-150 words) -->

<!-- What could be the biggest challenges/problems you might face? What is your plan B? -->

-   **Variation in GPS sampling frequency:** This may complicate trajectory extraction and similarity calculations. We may need to standardize temporal resolution or use weighted analysis.
-   **Computational limitations:** If processing times become excessive, we will reduce dataset size by focusing on a subset of individuals or specific time periods.

## Questions?

<!-- (100-150 words) -->

<!-- Which questions would you like to discuss at the coaching session? -->

-   Is the scope too broad? Should we focus on either revisited site analysis or movement similarity between individuals and sexes?
