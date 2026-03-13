# Google_Sheets_Progects

## 2021 Facebook Ad Campaigns ROMI


![2021 Facebook Campaign ROMI](https://github.com/user-attachments/assets/eefcee40-77ba-4630-a02c-16a4fe15a2e7)

I visualized the performance summary of Facebook ad campaigns using Google Sheets. This project aimed at both analyzing key marketing metrics and improving data visualization and formula proficiency in Google Sheets.   
🔍 Core technical methods used:\
 ✅ Data aggregation handled fully through the QUERY function (pivot tables only for KPIs).\
 ✅ Filtering applied via the WHERE clause inside the query (no slicers). For example:\
      =QUERY(ads_data_cleared2!A2:O1495; \
     "select K, B, sum(C), sum(D), sum(E), sum(F) \
     where O=2021 \ 
     and A >= date '" &  TEXT(Dashboard_laptop!G5; "yyyy-MM-dd") & "' \
     and A <= date '" & TEXT(Dashboard_laptop!G8; "yyyy-MM-dd") & "' \
     and B matches '"&B29&"' \
     group by K, B \
     order by K, B"; \
     -1) \
 ✅ A custom legend is used for the charts.\
 ✅ Candlestick chart colors adjusted with Apps Script (not directly adjustable in chart settings).
