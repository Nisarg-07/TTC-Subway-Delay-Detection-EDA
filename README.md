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

## Data Prepration
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

## EDA 
**1 TTC Subway Map**<br>
<br>
<img width="990" alt="Screenshot 2024-07-17 at 11 05 49 AM" src="https://github.com/user-attachments/assets/a96ddedf-5de0-48d4-a2b3-2e496ef85506"><br>
  <br>
- In the above scatter plot each **scatter represent** the **station** they are inter connected as per the subway line and by hovering mouse pointer we can get the **Line number**, **station name**, **longitude** and **Latitude** for that station.<br>
<br>


**2 Delay count in each line**
<img width="986" alt="Screenshot 2024-07-17 at 11 13 02 AM" src="https://github.com/user-attachments/assets/b610ceab-aff9-4bf8-bf96-48c1370ca417"><br>
<br>
- From the above bar graph we can say that there were **5170 incidents** noted in **Line number 1** which was hightest among all the subway lines.
<br>

**3 Delay count in bounds**
<img width="947" alt="Screenshot 2024-07-17 at 11 20 21 AM" src="https://github.com/user-attachments/assets/19065c23-9092-4b9a-9fd3-b0658170383e">
- Again from the above **piechart** the max delay can be seen in **North** and **south** bounds which is again **Line number 1**.

**4 Delay count in days**
<img width="988" alt="Screenshot 2024-07-17 at 12 21 59 PM" src="https://github.com/user-attachments/assets/59b209b5-6f2b-47d9-9f9f-3858b9dc6171">
- From the above pie chart it can be said that **higher delays** can be seen in the **weeks days** as lots of people travel to **Downtown** for the **work**, which really make sense.

**5 Sum of Min Delay by months**
<img width="988" alt="Screenshot 2024-07-17 at 12 35 29 PM" src="https://github.com/user-attachments/assets/27cc098e-68d6-4950-aca5-14cc11e82ace">
- In the month of **January** the total time between two trains in minutes was **exceptionally higher** which was a little over **7500 minutes**(we are considerng all of the 4 lines here).

**6 Delay trend in differnt hours**
<img width="988" alt="Screenshot 2024-07-17 at 12 41 44 PM" src="https://github.com/user-attachments/assets/aff27f03-e6d3-4c24-a715-f16a86386911">
- The **Min delay** around **6PM** was higher considering **employee rush** towards **home**.



