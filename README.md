# 2021 Facebook Ad Campaigns - Google_Sheets_project

## 📌 Project Overview
This project provides a comprehensive analysis of Facebook advertising performance throughout 2021, focusing on Return on Marketing Investment (ROMI) across various campaign categories. By evaluating metrics such as CPC, CPM, and CTR, the study identifies the efficiency of different marketing strategies, from brand awareness to wholesale promotions. The dashdoard visualizes the relationship between monthly ad spend and revenue generation, offering a data-driven view of campaign scalability and seasonal performance trends.

## Dashboard
![2021 Facebook Campaign ROMI](https://github.com/user-attachments/assets/eefcee40-77ba-4630-a02c-16a4fe15a2e7)

 👉 [Link to Google Sheets Dashboard](https://docs.google.com/spreadsheets/d/1SPnbiE7IHTZ6u0U26UlR4fqKciNLhHGld8tn6etdtoE/edit?usp=sharing)
 
 ## ⚒️ Core technical methods used:
 ✅ Data aggregation handled fully through the QUERY function (pivot tables only for KPIs).\
 ✅ Filtering applied via the WHERE clause inside the query (no slicers). For example:
 * Calculate the total revenue, spend, clicks, and impressions for each advertising campaign in each month, , with the ability to filter by a selected time period and advertising campaign.
 ```
      =QUERY(ads_data_cleared2!A2:O1495; 
     "select K, B, sum(C), sum(D), sum(E), sum(F) 
     where O=2021  
     and A >= date '" &  TEXT(Dashboard_laptop!G5; "yyyy-MM-dd") & "' 
     and A <= date '" & TEXT(Dashboard_laptop!G8; "yyyy-MM-dd") & "' 
     and B matches '"&B29&"' 
     group by K, B 
     order by K, B"; 
     -1) 
 ```
 ✅ Other advanced Google Sheets functions in this project:
 <details>
 <summary>FILTER and TRANSPOSE</summary>

 ```
 =TRANSPOSE(FILTER(E2:H12; E2:E12<>"Hobbies"; E2:E12<>"Expansion"))
 ```

 ```
 =FILTER(ads_data_cleared!J2:J1495; ads_data_cleared!J2:J1495<>0; ads_data_cleared!A2:A1495>=DATE(2021;1;1); ads_data_cleared!A2:A1495<=DATE(2021;12;31))

 ```

 </details>

 <details>
 <summary>SORT and UNIQUE</summary>

 ```
 =SORT(UNIQUE(Japan_candles!B2:B1155); 1; True)
 ```
 
 </details>

 <details>
 <summary>IFERROR and SUMIF</summary>

 ```
 =IFERROR(SUMIF(Spend_and_ROMI_by_campaign!$B$32:$B; C10; Spend_and_ROMI_by_campaign!$C$32:$C)/SUMIF(Spend_and_ROMI_by_campaign!$B$32:$B; C10; Spend_and_ROMI_by_campaign!$E$32:$E); "Was no campaign")
 ```

 </details>
 
 ✅ A custom legend is used for the charts.  
 ✅ Candlestick chart colors adjusted with Apps Script (not directly adjustable in chart settings).  

## 🔍 Project Insights

* <b>Revenue Impact:</b> Total advertising efforts resulted in $146,986 in revenue from a total spend of $115,287, proving the overall profitability of the marketing mix across the year.
* <b>Top Performing Campaigns:</b> The "Trendy" and "Promos" campaigns achieved the highest efficiency, with ROMI reaching 188.4% and 176.1% respectively, significantly outperforming the overall average of 127.5%.
* <b>Engagement Metrics:</b> The "Discounts" category demonstrated superior audience engagement with the highest CTR of 2.508% and the lowest CPC of $0.08, indicating highly relevant creative content for the target audience.
* <b>Spending Efficiency:</b> While the "Wholesale" campaign had the highest CPM ($4.89), its ROMI remained stable at 122.8%, suggesting that higher placement costs in this segment are balanced by conversion value.
* <b>Seasonal Scaling:</b> A significant scale-up in ad spend was observed starting in May 2021, peaking in July with a monthly investment of $20,723, which successfully maintained a stable ROMI throughout the high-spend period.
* <b>Consistency:</b> The "Daily ROMI Distribution" shows that most campaigns maintained tight performance clusters, though "Promos" and "Trendy" exhibited higher volatility alongside their higher returns.
   
