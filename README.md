# Project Name

## Table of Contents
1. [Background and Overview](#background-and-overview)
2. [Data Structure Overview](#data-structure-overview)
3. [Executive Summary](#executive-summary)
4. [Insights Deep Dive](#insights-deep-dive)
5. [Recommendations](#recommendations)

---

# Background and Overview
This report aims to analyze the hemodialysis vascular access market using Medicare claim data. The analysis utilized Medicare Part B data, which includes information on the utilization, payments, and submitted charges for services and procedures provided by healthcare professionals (HCPs). The report seeks to uncover market trends in this therapeutic domain and assess the commercial environment from the perspective of Humacyte, a biotech company specializing in bioengineered, off-the-shelf vascular grafts designed to provide durable and infection-resistant vascular access for patients requiring hemodialysis.

Insights and recommendations are provided in the following key areas:

- Overall Hemodialysis Market Analysis: A comprehensive review of hemodialysis claim trends, including total claims, the number of patients served, and market shifts over time, with a focus on key metrics like claim volume and coverage percentage.
- Regional Claim Comparison: A comparative analysis of hemodialysis claims across regions, highlighting geographic differences in year-over-year (YOY) total claim growth, changes in coverage percentage, and patterns of service usage.
- Hemodialysis Vascular Access Claims Breakdown: An analysis of claims based on the three primary types of vascular access for hemodialysis currently in practice (Arteriovenous (AV) Fistula, Arteriovenous (AV) Graft, and Central Venous Catheter (CVC)).
- Provider Type Analysis: An evaluation of claims by provider types (e.g., nephrologists, nurse practitioners), addressing questions such as which providers are delivering these services, the market size of each specialty, and identifying potential opportunities for commercial initiatives.

Example:
> This project focuses on analyzing customer and sales data for **Elist Electronics**, a global e-commerce company established in 2018. The main goal is to evaluate product performance, customer loyalty, and provide recommendations for improving commercial success.
![image](https://github.com/user-attachments/assets/a6c14a3b-b126-4b2e-8ef9-afe7de3498e0)

You can find the source to the datesets here.
You can find the Tableau Dashboard here.


---

# Data Structure Overview
The Medicare dataset contains the columns listed below, with a total row count of 377,744 after the filtering conditions have been applied and the datasets from 2017 to 2022 have been joined
- `Rndrng_NPI`: National Provider Identifier.
- `Rndrng_Prvdr_Last_Org_Name`: Last Name/Organization Name of the Provider.
- `Rndrng_Prvdr_First_Name`: First Name of the Provider.
- `Rndrng_Prvdr_MI`: Middle Initial of the Provider.
- `Rndrng_Prvdr_Crdntls`: Credentials of the Provider.
- `Rndrng_Prvdr_Gndr`: Gender of the Provider.
- `Rndrng_Prvdr_Ent_Cd`: Entity Type of the Provider.
- `Rndrng_Prvdr_St1`: Street Address 1 of the Provider.
- `Rndrng_Prvdr_St2`: Street Address 2 of the Provider.
- `Rndrng_Prvdr_City`: City of the Provider.
- `Rndrng_Prvdr_State_Abrvtn`: State Abbreviation of the Provider.
- `Rndrng_Prvdr_State_FIPS`: State FIPS Code of the Provider.
- `Rndrng_Prvdr_Zip5`: Zip Code of the Provider.
- `Rndrng_Prvdr_RUCA`: RUCA Code of the Provider.
- `Rndrng_Prvdr_RUCA_Desc`: RUCA Description.
- `Rndrng_Prvdr_Cntry`: Country Code of the Provider.
- `Rndrng_Prvdr_Type`: Provider Type of the Provider.
- `Rndrng_Prvdr_Mdcr_Prtcptg_Ind`: Medicare Participation Indicator.
- `HCPCS_Cd`: HCPCS Code.
- `HCPCS_Desc`: HCPCS Description.
- `HCPCS_Drug_Ind`: HCPCS Drug Indicator.
- `Place_Of_Srvc`: Place of Service.
- `Tot_Benes`: Number of Medicare Beneficiaries.
- `Tot_Srvcs`: Number of Services.
- `Tot_Bene_Day_Srvcs`: Number of Distinct Medicare Beneficiary/Per Day Services.
- `Avg_Sbmtd_Chrg`: Average Submitted Charge Amount.
- `Avg_Mdcr_Alowd_Amt`: Average Medicare Allowed Amount.
- `Avg_Mdcr_Pymt_Amt`: Average Medicare Payment Amount.
- `Avg_Mdcr_Stdzd_Amt`: Average Medicare Standardized Payment Amount.

Code Snippet 
```sql
CREATE TABLE medicare_data_2017_2022_revised AS
SELECT *
FROM medicare_data_2017 t2017
WHERE hcpcs_cd IN (
  'X2R50WA', 'X2R60WA', 'X2R70WA', 'X2R80WA',
  'C1769', 'G0365', 'C1874', '36830',
  'C1884', 'C1753', '36818', '36821',
  '37799', 'C2623', '93970', 'G0392', 'G0269',
  '90935', '90937', '90945', '90947', '90999',
  'G0257', 'G0308', 'G0309', 'G0310', 'G0311', 'G0312', 'G0313',
  'G0314', 'G0315', 'G0316', 'G0317', 'G0318', 'G0319', 'G0320', 
  'G0321', 'G0322', 'G0323', 'G0324', 'G0325', 'G0326', 'G0327', 
  '36800', '36810', '36819', '36820', '36821', '36825', '36832', 
  '36833', '36834', '36831', '36901', '36902', '36558'
)
UNION ALL
SELECT *
FROM medicare_data_2018 t2018
WHERE hcpcs_cd IN (
  'X2R50WA', 'X2R60WA', 'X2R70WA', 'X2R80WA',
  'C1769', 'G0365', 'C1874', '36830',
  'C1884', 'C1753', '36818', '36821',
  '37799', 'C2623', '93970', 'G0392', 'G0269',
  '90935', '90937', '90945', '90947', '90999',
  'G0257', 'G0308', 'G0309', 'G0310', 'G0311', 'G0312', 'G0313',
  'G0314', 'G0315', 'G0316', 'G0317', 'G0318', 'G0319', 'G0320', 
  'G0321', 'G0322', 'G0323', 'G0324', 'G0325', 'G0326', 'G0327', 
  '36800', '36810', '36819', '36820', '36821', '36825', '36832', 
  '36833', '36834', '36831', '36901', '36902', '36558'
)
UNION ALL
SELECT *
FROM medicare_data_2019 t2019
WHERE hcpcs_cd IN (
  'X2R50WA', 'X2R60WA', 'X2R70WA', 'X2R80WA',
  'C1769', 'G0365', 'C1874', '36830',
  'C1884', 'C1753', '36818', '36821',
  '37799', 'C2623', '93970', 'G0392', 'G0269',
  '90935', '90937', '90945', '90947', '90999',
  'G0257', 'G0308', 'G0309', 'G0310', 'G0311', 'G0312', 'G0313',
  'G0314', 'G0315', 'G0316', 'G0317', 'G0318', 'G0319', 'G0320', 
  'G0321', 'G0322', 'G0323', 'G0324', 'G0325', 'G0326', 'G0327', 
  '36800', '36810', '36819', '36820', '36821', '36825', '36832', 
  '36833', '36834', '36831', '36901', '36902', '36558'
)
UNION ALL
SELECT *
FROM medicare_data_2020 t2020
WHERE hcpcs_cd IN (
  'X2R50WA', 'X2R60WA', 'X2R70WA', 'X2R80WA',
  'C1769', 'G0365', 'C1874', '36830',
  'C1884', 'C1753', '36818', '36821',
  '37799', 'C2623', '93970', 'G0392', 'G0269',
  '90935', '90937', '90945', '90947', '90999',
  'G0257', 'G0308', 'G0309', 'G0310', 'G0311', 'G0312', 'G0313',
  'G0314', 'G0315', 'G0316', 'G0317', 'G0318', 'G0319', 'G0320', 
  'G0321', 'G0322', 'G0323', 'G0324', 'G0325', 'G0326', 'G0327', 
  '36800', '36810', '36819', '36820', '36821', '36825', '36832', 
  '36833', '36834', '36831', '36901', '36902', '36558'
)
UNION ALL
SELECT *
FROM medicare_data_2021 t2021
WHERE hcpcs_cd IN (
  'X2R50WA', 'X2R60WA', 'X2R70WA', 'X2R80WA',
  'C1769', 'G0365', 'C1874', '36830',
  'C1884', 'C1753', '36818', '36821',
  '37799', 'C2623', '93970', 'G0392', 'G0269',
  '90935', '90937', '90945', '90947', '90999',
  'G0257', 'G0308', 'G0309', 'G0310', 'G0311', 'G0312', 'G0313',
  'G0314', 'G0315', 'G0316', 'G0317', 'G0318', 'G0319', 'G0320', 
  'G0321', 'G0322', 'G0323', 'G0324', 'G0325', 'G0326', 'G0327', 
  '36800', '36810', '36819', '36820', '36821', '36825', '36832', 
  '36833', '36834', '36831', '36901', '36902', '36558'
)
UNION ALL
SELECT *
FROM medicare_data_2022 t2022
WHERE hcpcs_cd IN (
  'X2R50WA', 'X2R60WA', 'X2R70WA', 'X2R80WA',
  'C1769', 'G0365', 'C1874', '36830',
  'C1884', 'C1753', '36818', '36821',
  '37799', 'C2623', '93970', 'G0392', 'G0269',
  '90935', '90937', '90945', '90947', '90999',
  'G0257', 'G0308', 'G0309', 'G0310', 'G0311', 'G0312', 'G0313',
  'G0314', 'G0315', 'G0316', 'G0317', 'G0318', 'G0319', 'G0320', 
  'G0321', 'G0322', 'G0323', 'G0324', 'G0325', 'G0326', 'G0327', 
  '36800', '36810', '36819', '36820', '36821', '36825', '36832', 
  '36833', '36834', '36831', '36901', '36902', '36558'
);

```
You may also include any initial data checks or processing steps performed (e.g., data cleaning, removing duplicates, handling null values).
![image](https://github.com/user-attachments/assets/8a341b2e-a0b0-4343-99b5-72d19c0dcbcd)

---

# Executive Summary
## Overview of Findings 
After a marginal growth from 2017 to 2019 and peaking at 2019 at 1.24 billion, the total claim (payment made by Medicare) for hemodialysis vascular access related claims has fallen steadily since, showing negative YOY growth from 2020 to 2022. While this decline can be attributed to impact of COVID, other factors such as higher kidney transplant rate, increase uptake of at-home dialysis (At the end of 2020, 13.7% of all patients undergoing dialysis performed dialysis at home. The percentage of patients performing home dialysis increased approximately 50% between 2010 and 2020) and improvements in preventative care all contributed to its decline. 

Below is the overview page form the Tableau dashboard and more examples are included throughout the report. The entire interactive dashboard can be accessed here. 

![Dashboard 1 (3)](https://github.com/user-attachments/assets/4b67209c-f1e6-4701-b316-5852da9f4e70)
Example:
- **2022 Revenue**: $5M (YoY -45.7%)
- **2022 Order Volume**: 21,565 (YoY -39.9%)
- **2022 Average Order Value (AOV)**: $229.91 (YoY -9.7%)

While revenue and order volume declined in 2022, the **Average Order Value** showed some resilience due to an increase in high-cost product sales.
![image](https://github.com/user-attachments/assets/f737d2e0-bd50-4a82-a388-156cff396ce8)

---

# Insights Deep Dive

### Overall Hemodialysis Market Analysis
![image](https://github.com/user-attachments/assets/c8330668-0f35-4ab1-99f1-3cc73012e63b)
![image](https://github.com/user-attachments/assets/e6af07db-30da-4b72-95e8-bf8759fcceed)
### Regional Claim Comparison
### Hemodialysis Vascular Access Claims Breakdown
### Provider Type Analysis

### Example Insights:
Overall Trend analysis




Regional analsis
![image](https://github.com/user-attachments/assets/fe79df85-862a-44a4-a5a8-19b5c8d97f38)
![image](https://github.com/user-attachments/assets/2181dd81-ab03-42b5-8399-79394dc55e35)


- **Key Insight 1: Decline in Revenue**
    - The company’s revenue dropped by **45.7%** year-over-year in 2022.
    - Possible reason: Decrease in customer loyalty and order volume by **39.9%**.
    
- **Key Insight 2: High-Cost Products Resilience**
    - Despite the overall revenue drop, high-cost laptop orders saw a **10%** year-over-year increase in September 2022.
    - The increased sales of premium laptops compensated for losses in other product categories.
![image](https://github.com/user-attachments/assets/e7e5eb21-9c41-4fc5-9dd6-04f025239d3b)
![image](https://github.com/user-attachments/assets/f065488f-27be-4578-8e7e-2d1424496f96)

---

# Recommendations
Based on the insights, provide actionable recommendations for the business or client.

### Example Recommendations:

1. **Diversify the Product Portfolio**: 
   - With 85% of orders and 70% of revenue coming from just three products, diversifying the product portfolio is critical.
   - **Action**: Introduce new product lines, particularly in the higher-cost segments like premium laptops and accessories.

2. **Target Loyalty Program Members for Upsell**: 
   - Focus marketing efforts on converting non-members into loyalty members and upsell current loyalty members with personalized offers.
   - **Action**: Utilize personalized email campaigns and promotions based on loyalty program data.

3. **Re-evaluate Marketing for Underperforming Products**:
   - Products like the Bose SoundSport Headphones account for less than 1% of annual revenue and may not be worth continued focus.
   - **Action**: Consider discontinuing or repackaging underperforming products while focusing more on top-performing items.
![image](https://github.com/user-attachments/assets/334c4f84-2e15-420f-b7de-5d1726226e79)

---

This single-page README format keeps all the relevant project sections organized and easy to follow, providing an end-to-end report within the same document.
