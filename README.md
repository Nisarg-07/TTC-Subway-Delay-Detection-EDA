# TTC-Subway-Delay-Detection-EDA
>**Created by : Nisarg Patel**
- This project demostrate our findings on delay in TTC subway in a interactive form.
- We have used diverse visualization techniques to find out :
  - Maximum,minumum delays in subway lines.
  - Busier stations in each subway lines.
  - At what time the station is busier?
  - what are the reasons for the delay? and many more useful information.

## Code and resources used 
**Python version :** 3.11<br>
<br>
**Packages:** Pandas, Numpy, Seaborn, Plotly<br>
<br>
**Dataset:** https://open.toronto.ca/dataset/ttc-subway-delay-data/<br>
<br>
**Mapquest article:** https://developer.mapquest.com/documentation/api/geocoding/

## Dataset 
- We have used **City of Toronto open data portal** to collect the data - https://open.toronto.ca/dataset/ttc-subway-delay-data.
- The data belongs to year **2022** and it has total **20K** entries.
- We have also collected **Longitude** and **Latitude** for each **subway station** from each line using Mapquest API.

# Data Prepration
- **Removing Duplicates:**
  - There were **15 duplicate records** so we simply **drop** thoes records.
  <br>
- **Missing Values:**
  - There were **5536 missing values** in the **Bound** column. 
  - We **cannot predic**t which way the subway was going unless and untill we some sort of **proper direction**.
  - We could have **dropped** this column but our **focus** was **not to implement ML model** on **intuitive data**, Which is again **not a right practice**.
  - But here, our **focus** was to find **insights** we **replaced** **missing value** with **Unknown**.
  - **Line** column had **39 missing values**, based on **station column** we **imputed** right **subway line number**.
  <br>
- **Cleaning Station column:**
  - Instead of **75** station column has **259 unique** entries.
    - Includes (**spelling mistakes, Spacing issue, differnt names for similar stations**)
  - We used **Regex** to clean this column.
