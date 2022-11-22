## Bigquery SQL query

SELECT \* FROM gdelt-bq.gdeltv2.events
WHERE SQLDATE BETWEEN CAST(FORMAT_DATE("%Y%m%d", current_date()) AS INT64) - 200 and CAST(FORMAT_DATE("%Y%m%d", current_date()) AS INT64)
AND IsRootEvent = 1 AND Actor1Code IS NOT NULL AND Actor2Code IS NOT NULL
AND ActionGeo_Lat IS NOT NULL AND ActionGeo_Long IS NOT NULL
AND (Actor1Name = 'ORGANIZED CRIME' OR Actor2Name = 'ORGANIZED CRIME')
LIMIT 500;
# flythru
