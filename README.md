# ✈️ SkyFlow: Airline Delay Causes & Operational Analysis

An interactive, end-to-end Microsoft Power BI dashboard designed to visualize, analyze, and uncover the root causes of flight delays and cancellations in the United States. This project transforms over 1.9 million raw flight records into actionable operational insights for aviation stakeholders.

---

## Project Overview
Operating efficient airline schedules is a critical challenge. This project focuses on cleaning, modeling, and visualizing the comprehensive **Airline Delay Causes** dataset to provide airport operators and airlines with an intuitive tool to track, filter, and dissect delays by carrier, origin, destination, and key delay categories.

<img width="891" height="502" alt="Airline2" src="https://github.com/user-attachments/assets/306bb29f-8890-4f71-8be6-144203cbab73" />



### 🔍 Key Objectives:
*   Identify primary drivers of flight delays (Carrier, Weather, National Air System, Security, and Late Aircraft).
*   Analyze flight cancellation patterns and decode their operational reasons.
*   Enable seamless decision-making via interactive BI features (drill-downs, tooltips, and dynamic slicers).


---


## 📊 Dataset & Sources
The analysis utilizes the **2008 Airline Delay Causes** dataset sourced from [Kaggle](https://www.kaggle.com/datasets/giovamata/airlinedelaycauses?select=DelayedFlights.csv). 
*   **Scale:** Relies on `DelayedFlights.csv` containing detailed historical logs of domestic flights in the US.
*   **Data Integration:** Standardized and merged international airport databases to map IATA codes directly to real city and airport names.
*   **Transformation:** Cleaned missing delay values and translated cryptic cancellation codes (`A` = Carrier, `B` = Weather, `C` = NAS, `D` = Security) into human-readable categories.


---

## 🛠️ Dimensional Modeling
To ensure optimized performance and seamless filter propagation over millions of records, a robust **Star Schema** was implemented:
*   **DimDates:** Custom date dimension with a built-in hierarchy (Year > Quarter > Month > Day) for clean timeline analysis.
*   **DimCarriers / DimDest / DimOrigin:** Fast lookup tables mapping airlines and geographical routes based on IATA codes.
*   **DimCancellation:** Clean mapping table for operational cancellation causes.


<img width="983" height="553" alt="StarSchema" src="https://github.com/user-attachments/assets/9a8323f8-b449-4df2-951f-73e075f8d546" />

---


## 📏 Dedicated DAX Measures Table
All calculations and KPIs are isolated in a dedicated **`_Measures`** table to ensure clean model governance:
*   **Total Delay Minutes:** Cumulative delay across Carrier, Weather, NAS, Security, and Late Aircraft fields.
*   **Average Delay per Flight:** Dynamic calculation reacting to active slicers and parameters.

<img width="916" height="552" alt="Delay" src="https://github.com/user-attachments/assets/3513146a-0f45-4ca0-868c-188050daca0b" />


*   **On-Time Performance (OTP) %:** Percentage of flights arriving within the acceptable threshold.
*   **Cancellation Rate:** Percentage of scheduled flights that were cancelled.

  
  <img width="936" height="554" alt="Cancellation" src="https://github.com/user-attachments/assets/42e6b067-dc81-4a47-a326-1d001e11d146" />

  
---

## Dashboard Features & Visualizations
The report layout prioritizes a clean, user-centric **UI/UX** designed for seamless exploration:

*   **Executive KPI Cards:** Quick high-level overview of critical operational metrics.

*   **Geographical Map Integration:** Visualized flight paths, delay magnitudes, and airport traffic distribution across the US using interactive maps.


  <img width="936" height="546" alt="Map" src="https://github.com/user-attachments/assets/8e4ff3e8-7daa-4453-9e37-eb79cf124f21" />


*   **AI-Powered Q&A:** Integrated natural language processing (Q&A visual) to allow users to ask questions about delay causes in plain English and get instant visual answers.



<img width="932" height="545" alt="Q A" src="https://github.com/user-attachments/assets/b698c636-78d1-400d-947f-c88fb9b5e123" />



*   **Drill-Down Capabilities:** Easily dive from high-level yearly trends down to monthly and daily specifics.
*   **Drill-Through Actions:** Right-click on any specific carrier or airport to open a detailed performance sheet.

    
<img width="1081" height="552" alt="DrillThroughphoto" src="https://github.com/user-attachments/assets/d5650658-c281-4398-8c89-ff65af6abb15" />



<img width="944" height="551" alt="DrillThroughPage" src="https://github.com/user-attachments/assets/0ef17240-00cf-4419-a2c5-3f7dad426d68" />



*   **Custom Tooltips:** Hovering over charts reveals secondary contextual metrics without cluttering the canvas.


<img width="937" height="552" alt="ToolTip" src="https://github.com/user-attachments/assets/0ff9b867-e4fa-4d39-bccb-1ffc0f359382" />




<img width="731" height="551" alt="Tooltip Page" src="https://github.com/user-attachments/assets/947588ad-1f68-4153-b467-c89ad6936dfd" />



*   **Advanced Navigation:** Fully interactive dashboard integrated with synchronized slicers, bookmarks, and reset buttons.

---

## 🚀 How to View the Dashboard
Because the original `.pbix` file exceeds GitHub's file size limits (100MB), the full interactive Power BI report is hosted externally.

*   📥 **[Download the .PBIX File from Google Drive](https://drive.google.com/drive/folders/1Ih0J_mGH_x4Au1tqmiDI07q1FAsAwqV_?usp=sharing)**


*To run locally, download the file from the Google Drive link above and open it using **Microsoft Power BI Desktop**.*

---

## 🛠️ Tech Stack
*   **Data Cleaning & ETL:** Power Query (M Formula Language)
*   **Data Modeling:** Microsoft Power BI Desktop (Star Schema)
*   **Analytical Calculations:** DAX (Data Analysis Expressions)
*   **Data Source:** Kaggle (2008 Flight Delay Causes)




