# Analysis of Medicare Data for Vascular Access in Hemodialysis

## Table of Contents
1. [Background and Overview](#background-and-overview)
2. [Executive Summary](#executive-summary)
3. [Insights Deep Dive](#insights-deep-dive)
4. [Recommendations](#recommendations)
5. [Data Structure Overview](#data-structure-overview)

---

# Background and Overview
This report aims to analyze the hemodialysis vascular access market using Medicare claim data. The analysis utilized Medicare Part B data from 2017 to 2022, which includes information on the utilization, payments, and submitted charges for services and procedures provided by healthcare professionals (HCPs). The report seeks to uncover market trends in this therapeutic domain and assess the commercial environment from the perspective of Humacyte, a biotech company specializing in bioengineered, off-the-shelf vascular grafts designed to provide durable and infection-resistant vascular access for patients requiring hemodialysis.

Insights and recommendations are provided in the following key areas:

- Overall Hemodialysis Market Analysis: A comprehensive review of hemodialysis claim trends, including total claims, the number of patients served, and market shifts over time, with a focus on key metrics like claim volume and coverage percentage.
- Regional Claim Comparison: A comparative analysis of hemodialysis claims across regions, highlighting geographic differences in year-over-year (YOY) total claim growth, changes in coverage percentage, and patterns of service usage.
- Service Type Category Breakdown: An analysis of claims based on the three primary types of vascular access for hemodialysis currently in practice (Arteriovenous (AV) Fistula, Arteriovenous (AV) Graft, and Central Venous Catheter (CVC)).
- Provider Type Analysis: An evaluation of claims by provider types (e.g., nephrologists, nurse practitioners), addressing questions such as which providers are delivering these services, the market size of each specialty, and identifying potential opportunities for commercial initiatives.


You can find the source of the datasets [here](https://data.cms.gov/provider-summary-by-type-of-service/medicare-physician-other-practitioners/medicare-physician-other-practitioners-by-provider-and-service).

You can find the Tableau Dashboard [here](https://public.tableau.com/app/profile/chung.hsi.shan/viz/AnalysisofMedicareDataforVascularAccessinHemodialysis/Dashboard1).

---
# Executive Summary

### Overview of Findings 
Following marginal growth between 2017 and 2019, peaking in 2019 at $1.24 billion, total Medicare payments for hemodialysis vascular access-related claims have steadily declined, with negative year-over-year growth from 2020 to 2022. While this drop can largely be attributed to the impact of COVID-19, other contributing factors include higher kidney transplant rates, the growing adoption of at-home dialysis (by the end of 2020, 13.7% of all dialysis patients performed dialysis at home, marking a 50% increase between 2010 and 2020), and improvements in preventative care.

Medicare covers healthcare for 80% of patients in the U.S. with end-stage kidney disease (ESKD) (source), meaning this report reflects a significant portion of the costs associated with vascular access for hemodialysis in the U.S.

Below is the overview page from the Tableau dashboard, with additional examples included throughout the report. The full interactive dashboard can be accessed here.

![Dashboard 1 (3)](https://github.com/user-attachments/assets/4b67209c-f1e6-4701-b316-5852da9f4e70)

Top line Metrics for Hemodialysis Vascular Access Related Claims:
- **2022 Total Submitted Claim**: $3.1B (YoY -12.70%)
- **2022 Total Medicare Payment**: $898.4M (YoY -16.92%)
- **2022 Total Patient Serviced**: 3.905M
- **2022 Average Medicare Coverage Percentage**: 28.64%

---

# Insights Deep Dive

### Overall Hemodialysis Market Analysis:
> In 2022, Medicare care payment for claims related to hemodialysis vascular access amounted to $898.4M, with the total number of patients serviced being 3.9M (a single patient can be accounted for multiple times, this merely reflects the number of patient engagement). This is a drastic decrease from the year prior ($1.1B, YOY -16.92%) and highlights a downward trend that began in 2020. 

> Despite the downward trend, the percentage of Medicare coverage has remained steady from 2017 to 2022, with an average of 28.26% coverage throughout the 6-year period.

> ![image](https://github.com/user-attachments/assets/27b46e19-6971-457a-9754-bb921d35e7b4)


### Regional Claim Comparison
> The analysis focuses on the contiguous United States (excluding Hawaii and Alaska) and separates the country into 3 regions (West, Central, and East) to identify regional differences.

> In 2022, all three regions saw the largest decline in total Medicare payment growth (Year-over-Year: West -11.34%, Central -19.25%, East -17.73%). Prior to 2020, each region experienced marginal but positive growth, underscoring the impact of COVID-19 on hemodialysis care accessibility. This decline can also be linked to improvements in kidney transplants, increased use of at-home dialysis, and advancements in preventative care.

> Among the three regions examined, the West was the least impacted by the decline, with Medicare payments decreasing from $194.75M in 2017 to $168.31M in 2022. In contrast, the Central region saw a much steeper decline, from $250.83M to $176.19M, and the East region experienced the largest drop, going from $780.46M to $554.90M during the same period.

> ![image](https://github.com/user-attachments/assets/5b0f3bc7-3686-41ef-a39a-adbeecbc1faf)

> In terms of percentage coverage, the West consistently had the highest coverage compared to the other two regions, though the difference was only 1-2 percentage points each year. 

> ![image](https://github.com/user-attachments/assets/dec0fff3-d5df-48ab-948a-b0353158eb40)

### Service Type Category Breakdown
> The HCPCS codes have been organized by the type of service provided. For a detailed breakdown of the HCPCS code categorization, please refer to the Data Structure Overview section. The following categories were used in this analysis: AV Revision, AVF Creation, AVG Creation, CVC Insertion, CVC Others, CVC Removal, CVC Repair or Replacement, Dialysis Circuit Assessment, ESRD Services, and Hemodialysis Cannulation. It’s important to note that CVC-related categories are not specific to hemodialysis, and it is not possible to isolate the associated claims entirely. Therefore, the values presented may not fully reflect services related specifically to hemodialysis.

> Year-over-year Medicare payment growth across all HCPCS categories followed a similar pattern, with minor fluctuations between 2017 and 2020, and a sharp decline from 2020 onward. Claims related to AVF/AVG creation and revision have notably decreased in recent years. Although various factors, such as improved AVF/AVG durability and increased adoption of peritoneal dialysis, may have influenced this trend, the sharp decline is most likely driven by the impact of COVID-19. Further data is required to assess whether this trend will persist or if claims will rebound to pre-COVID levels.

> ![image](https://github.com/user-attachments/assets/ac5dcad9-322c-4f1f-a51c-643cbf631314)

> The average percentage of Medicare coverage remained relatively stable, with no significant fluctuations. ESRD services, which encompass dialysis management for ESRD patients, accounted for the highest coverage at 38.30%, significantly exceeding that of other categories.

> In contrast, services related to CVCs (insertion, removal, repair, replacement, or other procedures) had the lowest coverage among the various types of vascular access. This is consistent with clinical practice guidelines, as CVCs are typically the third option for long-term hemodialysis, following AVF and AVG.

> ![image](https://github.com/user-attachments/assets/0ff5b8c8-fc5b-419a-a81b-660fac465865)

> Among the three main types of vascular access, claims for AV revision procedures (which address complications such as stenosis or thrombosis in AVF or AVG to restore hemodialysis access) represent an average of 61.36% of the total procedures. ESRD services have been excluded from this analysis as they do not directly relate to vascular access types. This is significantly higher than the second-largest category, CVC insertion, which represents 27.67% and is not exclusively used for hemodialysis.

> This highlights an unmet clinical need, as AVFs and AVGs, though the preferred options for establishing vascular access, frequently encounter complications requiring corrective procedures. This places a considerable burden on patients, who must endure repeated interventions and potential complications, while also straining Medicare, as a significant portion of funds are allocated to these revision procedures.

> ![image](https://github.com/user-attachments/assets/d286fc9f-c852-405f-9fa3-5b7341f0470c)

### Provider Type Analysis
> A close examination of the provider type breakdown shows that Nephrology remains the largest spender, representing approximately 64% ($581M) of total Medicare payments annually, despite the overall decline in the segment. Meanwhile, Ambulatory Surgical Centers saw significant growth, increasing from just 2.75% ($33.4M) of total payments to 11.81% ($106.1M) in 2022, making it the second-largest provider type.

> Other provider types have maintained a consistent share over the 6-year period, with no significant fluctuations or major shifts observed in their portion of the total Medicare payment.  

> ![image](https://github.com/user-attachments/assets/edc748ea-4104-46f4-afaa-e71aa9395bef)

> A deeper analysis of the service type categories revealed the reason behind the significant rise in Ambulatory Surgical Centers. Initially accounting for just 8.30% ($25.9M) of AV revision-related services, these centers have steadily increased their share in this category, reaching a peak of 43.99% ($89.7M) in 2022. In contrast, Nephrology's share has gradually declined, dropping from 36.42% ($113.8M) to just 21.12% ($43.1M) in 2022.

> ![image](https://github.com/user-attachments/assets/1d4b1a0b-6416-4f20-995d-3733d5d97407)
---

# Recommendations
Based on the uncovered insights, the following recommendations have been provided: 
- With the rapid growth of Ambulatory Surgical Centers' claims in AV revisions, this provider type presents a valuable opportunity for commercial engagement. ASCs could serve as a key customer segment for promoting and advocating for vascular access methods that are more durable and have fewer complications.
- Given the regional disparity, it is worthwhile to investigate further the causes behind the large reduction in claims in the East. Factors such as regional healthcare policies, demographic shifts, or other regulatory changes could be contributing to this trend. Understanding the root causes can provide strategic insights into regional healthcare dynamics, helping assess commercial launch favorability and tailor strategies to each region's specific characteristics.
- When negotiating reimbursement rates, emphasizing the significant cost and high percentage of payments related to AV revision procedures could be advantageous. Since AV revisions account for a large portion of overall claims, payers may recognize the financial burden these procedures place on the healthcare system. By underscoring the frequency and cost of addressing complications like stenosis and thrombosis in AVF or AVG, it can strengthen the case for better reimbursement rates.


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
  '36555', '36556', '36557', '36558', '36560', '36561', '36563', '36565',
  '36566', '36568', '36569', '36570', '36571', '36572', '36573', '36575',
  '36576', '36578', '36580', '36581', '36582', '36583', '36584', '36585',
  '36589', '36590', '36591', '36592', '36593', '36595', '36596', '36597', '36598',
  '36800', '36810', '36815', '36818', '36819', '36820', '36821', '36825', '36830',
  '36831', '36832', '36833', '36835', '36836', '36837', '36838', '36860', '36861',
  '36901', '36902', '36903', '36904', '36905', '36906', '36907', '36908', '36909',
  '90935', '90937', '90940', '90945', '90947', '90951', '90952', '90953', '90954',
  '90955', '90956', '90957', '90958', '90959', '90960', '90961', '90962', '90963',
  '90964', '90965', '90966', '90967', '90968', '90969', '90970'
)
UNION ALL
SELECT *
FROM medicare_data_2018 t2018
WHERE hcpcs_cd IN (/* same hcpcs_cd list as above */)
UNION ALL
SELECT *
FROM medicare_data_2019 t2019
WHERE hcpcs_cd IN (/* same hcpcs_cd list as above */)
UNION ALL
SELECT *
FROM medicare_data_2020 t2020
WHERE hcpcs_cd IN (/* same hcpcs_cd list as above */)
UNION ALL
SELECT *
FROM medicare_data_2021 t2021
WHERE hcpcs_cd IN (/* same hcpcs_cd list as above */)
UNION ALL
SELECT *
FROM medicare_data_2022 t2022
WHERE hcpcs_cd IN (/* same hcpcs_cd list as above */);


```

### Categories of HCPCS codes

**CVC Insertion**
- 36556, 36558, 36561, 36563, 36565, 36566, 36569, 36571, 36573
- 90935, 90937, 90945, 90947, 90999

**CVC Repair or Replacement**
- 36575, 36580, 36581, 36582, 36583, 36584, 36585

**CVC Removal**
- 36589, 36590

**CVC Others**
- 36591, 36592, 36593, 36595, 36596, 36597, 36598

**Hemodialysis Cannulation**
- 36800, 36810, 36815

**AVF Creation**
- 36818, 36819, 36820, 36821, 36825

**AVG Creation**
- 36830

**AV Revision**
- 36831, 36832, 36833, 36838
- 36902, 36903, 36904, 36905, 36906, 36907, 36908, 36909

**Dialysis Circuit Assessment (AV Only)**
- 36901

**ESRD Services**
- 90960, 90961, 90962, 90965, 90966, 90970

---

