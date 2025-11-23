# ANALYSIS OF  MAP (Population per 500m Grid Cell)

- Map shows the total number of people living in each grid cell.

- Population = absolute people count

- Analysis of Map — Population per 500m Grid (Absolute Population)

### ✔ What This Map Shows

The total number of people living inside each grid cell, regardless of area.

Color Meaning:

- Dark red = 6,000–8,700 people

- Medium red = 4,800–6,000

- Orange = 3,600–4,800

- Yellow/cream = ~2,000 or less

### ✔ Key Observations

1️⃣ Central & North-Western Indirapuram have the highest populations These areas hold 7,000–8,700 people per 500m block, showing:

- High occupancy per building

- Dense apartment clusters

- Popular residential pockets

2️⃣ Some grid cells with medium population still show high density This happens when:

- A cell has few buildings, but each is very crowded

- Lots of mid-rise apartments packed into small areas

3️⃣ Sparse population cells are aligned with open spaces The lightest regions match:

- Parks

- Playgrounds

- Empty lots

- Commercial complexes

- Main roads


# Analysis of the MAP (Population Density Hotspots (People per km²)

- Map shows how crowded each grid cell is

- Density = pressure on area (crowding)

### ✔ What the Map Shows

This map highlights how tightly people are packed into each 500m cell.

Color Meaning:

- *Dark teal *= extremely high density (20,000–38,000 people per km²)

- Medium teal = 16,000–20,000 people/km²

- Light blue = lower density

- White/light areas = low or no residential population

### ✔ Key Observations

1️⃣ Northern Indirapuram is the densest zone The top-left to center-left region shows continuous dark teal, indicating:

- Many multi-storey apartment complexes

- Very little open space

- High occupancy residential blocks

- These are typically localities like:

 - Gyan Khand parts

- Shipra Suncity dense pockets

2️⃣ Some central pockets are surprisingly sparse White/light patches in the middle indicate:

- Parks

- Open grounds

- Commercial buildings

- Road intersections

- Under-construction or institutional areas

3️⃣ Density drops toward the southern edge South/south-east zones have fewer dark colors:

- More open plots

- Wider roads

- Lower-rise housing


# .csv Table Analysis 

Summary of population per grid:
 count     195.000000
mean     4075.566851
std      2166.372182
min        11.478696
25%      2340.778320
50%      4240.894043
75%      5634.140869
max      8711.384766
Name: pop_sum, dtype: float64

Top 10 most populated cells:
iD      pop_sum  pop_density_km2
60  8711.384766     34845.539062
63  8470.797852     33883.191406
59  8281.330078     33125.320312
33  8274.172852     33096.691406
58  8160.194824     32640.779297
32  7931.390625     31725.562500
62  7691.950195     30767.800781
99  7601.227051     30404.908203
49  7554.867676     30219.470703
37  7494.212402     29976.849609

***ANALYSIS ***
**Study area **(Indirapuram, Ghaziabad) was divided into 195 grid cells, each measuring 500m × 500m.

For each grid cell, total population was extracted from the WorldPop 2025 dataset.

📌 Key Statistics (What They Tell Us)

Metric	Meaning	Interpretation
- count = 195	Number of grid cells	Indirapuram is covered by 195 analysis units
- mean = 4,075 people	Average population per grid	A typical 500m cell contains ~4,000 people
- std = 2,166	Variation in population	High density variation; some cells are far more populated
- min = 11 people	Least populated cell	Likely parks, open spaces, or non-residential areas
  - 25% = 2,340 people	Lower-density quartile	25% of cells have fewer than ~2,300 people
  - 50% (median) = 4,240	Middle population	Half the area has fewer than ~4,200 people
  - 75% = 5,634	High-density quartile	25% of the area exceeds ~5,600 people per cell
- max = 8,711 people	Highest-density cell	Densest cluster in Indirapuram, extremely urbanized

### 🎯 What This Means in Simple Words

- Most of Indirapuram is moderately to highly populated, with 4,000–5,500 people per 500m block.

- There is strong density contrast: some cells have only a few dozen people (parks, roads), while dense apartment clusters host 7,000–8,700 people.

- This confirms Indirapuram is a high-density residential node of NCR.

### 🔥 Top 10 Most Populated Cells (Hotspots)

- The following grid cells show extremely high population values:

Grid ID	Population	Density (per km²)
60	8,711	34,845
63	8,470	33,883
59	8,281	33,125
33	8,274	33,097
58	8,160	32,640
32	7,931	31,725
62	7,691	30,767
99	7,601	30,404
49	7,554	30,219
37	7,494	29,976

🌆 Interpretation of Hotspots

These cells represent the densest residential blocks in Indirapuram:

- High-rise apartment clusters

- Compact multi-storey housing

- Areas with minimum open space

- Classic NCR high-density urban morphology

- Density values over 30,000 people per km² are extremely high and comparable to the densest parts of:

  - Mumbai suburbs

  - South Delhi colonies

  - Gurugram's apartment belts

- Urban Planning Meaning
This analysis highlights:

- Infrastructure demand zones

- High-service-pressure cells (water, electricity, waste)

- Potential congestion hotspots

- Areas suitable for targeted mobility planning

- Zones where social amenities may need reinforcement

# Combined Insight From Both Maps Together

By comparing Population Hotspots + Density Hotspots, you get deeper understanding:

🔍 If a cell is:

  - High population + High density → Severe pressure zone

  - High population + Moderate density → Balanced apartment zones

  - Low population + High density → Few buildings but extremely crowded

  - Low population + Low density → Open areas, parks, commercial roads


## ANALYSIS About Indirapuram’s Urban Structure

What This Means About Indirapuram’s Urban Structure ✔ Indirapuram is a classic NCR high-density township

- Most population clusters are above 4,000–6,000 people per 500m cell.

  - ✔ Residential blocks are extremely compact

- High population AND high density in multiple cells

- Very little open space in some mid-northern parts

  - ✔ Urban planning pressure is high in hotspot cells:

    - Water supply demand

    - Waste generation

    - Mobility congestion

    - Public safety load

    - Green space deficits

  - ✔ Southern and central pockets show opportunity zones

  - Could support new infrastructure

  - More open space

  - Lower population footprint


# FINAL SUMMARY ANALYSIS
“In Indirapuram, population per 500m grid ranges from as low as 11 people to as high as 8,700 people per cell. When we convert this to density, the hotspot regions cross 30,000 to 38,000 people per km², indicating extremely compact urban settlements.

The densest regions appear in the north-west and central sectors — areas dominated by multi-storey apartments. Meanwhile, the lighter zones reveal parks, commercial pockets, and open spaces.

Together, these maps help planners identify where services and infrastructure need to be strengthened, where population pressure is highest, and which areas can support future growth.”

