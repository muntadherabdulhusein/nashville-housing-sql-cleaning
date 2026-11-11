# Nashville Housing – Data Cleaning in SQL

A practice project where I cleaned a raw housing dataset from Nashville using SQL Server. I built it while following Alex The Analyst's data analyst portfolio series, to practise the typical cleaning steps you need before any analysis.

## What the script does

- **Standardise dates:** convert `SaleDate` from datetime to a simple date
- **Fill missing addresses:** some rows had no `PropertyAddress`, but other sales of the same `ParcelID` did, so I filled them with a self join and `ISNULL`
- **Split addresses into columns:** separate address, city and state using `SUBSTRING` / `CHARINDEX` and `PARSENAME`
- **Make values consistent:** change "Y" / "N" to "Yes" / "No" in `SoldAsVacant` with a `CASE` statement
- **Remove duplicates:** find duplicate sales with `ROW_NUMBER()` in a CTE and delete them
- **Drop unused columns** after the new clean ones were created

## SQL used

`CONVERT`, `ALTER TABLE` / `UPDATE`, self `JOIN`, `ISNULL`, `SUBSTRING`, `CHARINDEX`, `PARSENAME`, `CASE`, CTE with `ROW_NUMBER() OVER (PARTITION BY ...)`

## File

- `sql project Nashville.sql`: the full cleaning script, step by step with comments
