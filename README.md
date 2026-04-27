# Tech Layoffs Data Cleaning – MySQL

### Tools
MySQL

### What was wrong with the raw data
1. Duplicate rows
2. Industry names not standard – 'crypto', 'CryptoCurrency', 'crypto trading'
3. Null values in `industry` and `total_laid_off`

### How I fixed it
1. Used `ROW_NUMBER() OVER (PARTITION BY...)` to find and delete duplicates
2. `UPDATE layoffs SET industry = 'crypto' WHERE industry LIKE 'crypto%'` to standardize
3. Set nulls to 'Unknown' so they don't break analysis

### Files in this folder
- `SQL Analysis` – Full cleaning script with comments
- `cleaned data.csv` – Final dataset after cleaning
