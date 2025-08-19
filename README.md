# PAN Number Validation using SQL  

## Project Overview  
This project focuses on **validating PAN (Permanent Account Number) records** using SQL.  
The goal is to clean, validate, and categorize PAN numbers into **Valid** and **Invalid** based on specific rules.  

---

##  Objectives  
- Clean raw PAN data (handle nulls, duplicates, spacing, and case).  
- Validate PAN numbers against standard patterns.  
- Apply business rules like **no adjacent repetition** and **no sequential characters**.  
- Generate a summary report of **Valid vs Invalid PANs**.  

---

##  Data Source  
- **Input:** PAN numbers stored in a staging table (`stg_pan_numbers_dataset`).  
- **Output:** Cleaned & validated dataset (`pan_numbers_dataset_cleaned` and `vw_valid_invalid_pans`).  

---

##  Project Workflow  
1. **Data Cleaning**  
   - Handle missing and null values.  
   - Remove duplicates.  
   - Trim extra spaces.  
   - Standardize case (convert to uppercase).  

2. **SQL Techniques Used** 
- **CTEs (Common Table Expressions):** For stepwise data cleaning and validation.  
- **Views:** Created `vw_valid_invalid_pans` to categorize PAN numbers.  
- **Joins:** Used in the final step to compare cleaned PANs with validated PANs. 

3. **Validation Rules**  
   - PAN format must follow: `^[A-Z]{5}[0-9]{4}[A-Z]$`.  
   - No adjacent repeating characters.  
   - No sequential characters in alphabetic or numeric positions.  

4. **Final Categorization**  
   - View `vw_valid_invalid_pans` marks each PAN as **Valid** or **Invalid**.  

5. **Summary Report**  
   - Total processed records.  
   - Count of valid PANs.  
   - Count of invalid PANs.  
   - Count of incomplete or missing PANs.  
