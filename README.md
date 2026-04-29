# Digital-Rural-Pilot-Environments-and-Farmers-Green-Technology-Adoption

---

## 1. Dataset Overview

This dataset contains structured household survey data collected from rural farming households across four provinces of China, designed to investigate the effects of the Digital Rural Pilot Policy on green agricultural technology adoption. The data support empirical analyses using OLS, Poisson, Logit regression, and related methods.

| Attribute | Description |
|-----------|-------------|
| File name | formal_survey_data.xlsx |
| Sheet | data |
| Observations | 1,440 households |
| Variables | 147 columns |
| Survey year | 2023–2024 |
| Geographic coverage | 4 provinces, 16 counties, multiple villages |
| Treatment design | Quasi-experimental: pilot group (试点) vs. control group (对照) |
| Unit of observation | Household (one respondent per household) |
| Language | Variable names: English; Survey response values: Chinese |
| File format | Microsoft Excel (.xlsx) |

---

## 2. Study Background

China's Digital Rural Pilot Policy (数字乡村试点政策) designates selected counties as pilots for accelerated rural digital infrastructure development, including broadband expansion, e-commerce platforms, and digital agricultural services. This study uses a quasi-experimental design comparing pilot and non-pilot villages to identify policy effects on household-level adoption of seven core green agricultural technologies:

- Soil formula fertilization (配方施肥)
- Organic fertilizer application (有机肥施用)
- Pesticide reduction technology (减农药技术)
- Biological pest control (生物防控)
- Water-saving irrigation (节水灌溉)
- Straw returning to field (秸秆还田)
- Digital farm monitoring (数字化监测)

---

## 3. Geographic Coverage

Households were sampled from 4 provinces spanning distinct agro-ecological and socioeconomic contexts:

| Province | Counties | Agricultural Type |
|----------|----------|-------------------|
| Hubei (湖北) | Zigui (秭归县), Yicheng (宜城市), Xingshan (兴山县), Zaoyang (枣阳市) | Mountain Specialty Fruit / Plains Grain Production |
| Sichuan (四川) | Dayi (大邑县), Chongzhou (崇州市), Gong (珙县), Xingwen (兴文县) | Chengdu Plains Modern Agriculture / Mountain Specialty |
| Guangxi (广西) | Fuchuan (富川瑶族自治县), Gongcheng (恭城瑶族自治县), Pingle (平乐县), Zhongshan (钟山县) | Southern Mountain Specialty / Ethnic Minority Region |
| Heilongjiang (黑龙江) | Yi'an (依安县), Keshan (克山县), Huanan (桦南县), Huachuan (桦川县) | Northeast Large-Scale Grain / Black Soil Belt Grain-Soybean |

Within each county, villages were assigned to pilot or control status based on official policy designation. Households were selected using a systematic sampling approach within each village.

---

## 4. File Structure

The Excel file contains a single sheet named `data`. Each row represents one surveyed household. The 147 columns are organized into five thematic sections:

| Section | Columns | Content |
|---------|---------|---------|
| A: Sampling & Administrative | 1–28 | Geographic identifiers, village-level policy and infrastructure variables, county/province-level indices, outlier flags |
| B: Household Characteristics | 29–45 (Q1–Q17) | Respondent demographics, household size, land use, income, cooperative membership, training history |
| C: Green Technology Adoption | 46–66 (Q18) | Adoption status, year of adoption, and persistence (≥2 years) for each of 7 green technologies |
| D: Perceptions & Digital Use | 67–121 (Q19–Q65) | Non-adoption reasons, perceived effects, smartphone/internet use, digital skill capabilities, financing access, risk perceptions, trust in platforms, policy awareness; includes 3 open-ended text fields |
| E: Constructed Variables | 122–147 (gt_* / adopt_*) | Researcher-constructed adoption status categories, area share bands, strict/persistent adoption indicators, and aggregate counts |

---

## 5. Variable Codebook

For Likert-scale items: 1 = strongly disagree / not at all, 5 = strongly agree / very much, unless otherwise noted. Binary variables: 0 = No, 1 = Yes. Year variables record the calendar year of first adoption; blank cells indicate the technology was not adopted.

### Section A: Sampling & Administrative Variables (Cols 1–28)

| Variable Name | Col | Type | Description |
|---------------|-----|------|-------------|
| record_id | 1 | string | Unique household identifier (e.g., HH0001) |
| province | 2 | string | Province name (湖北/四川/广西/黑龙江) |
| county | 3 | string | County name |
| village | 4 | string | Village name (coded as county-number) |
| group | 5 | string | Treatment group: 试点 (pilot) / 对照 (control) |
| county_type | 6 | string | County agricultural typology (9 categories) |
| village_profile | 7 | string | Village type English label |
| village_network_score | 8 | numeric | Village internet infrastructure score (integer) |
| village_digital_project | 9 | binary | Village has digital rural pilot project (0/1) |
| village_agri_service_station | 10 | binary | Village has agricultural service station (0/1) |
| village_ecommerce_station | 11 | binary | Village has e-commerce service station (0/1) |
| village_green_demo_project | 12 | binary | Village has green technology demonstration project (0/1) |
| village_lead_industry | 13 | string | Village dominant agricultural industry |
| county_treatment_strength | 14 | numeric | County-level treatment intensity (continuous) |
| county_development | 15 | numeric | County economic development index |
| province_green_effect | 16 | numeric | Province-level green policy effect score |
| province_digital_effect | 17 | numeric | Province-level digital infrastructure effect score |
| province_market_effect | 18 | numeric | Province-level market access effect score |
| province_finance_effect | 19 | numeric | Province-level rural finance effect score |
| village_cluster_green | 20 | numeric | Village cluster score: green technology dimension |
| village_cluster_digital | 21 | numeric | Village cluster score: digital infrastructure dimension |
| village_cluster_market | 22 | numeric | Village cluster score: market access dimension |
| village_cluster_finance | 23 | numeric | Village cluster score: rural finance dimension |
| household_no_in_village | 24 | integer | Household sequence number within village |
| interview_month | 25 | integer | Month of interview (1–12) |
| cadre_present | 26 | binary | Village cadre was present during interview (0/1) |
| hh_outlier_flag | 27 | binary | Household flagged as outlier (0/1) |
| hh_outlier_type | 28 | string | Outlier type: high_performer / low_performer / blank |

### Section B: Household & Respondent Characteristics (Q1–Q17, Cols 29–45)

| Variable Name | Col | Type | Description |
|---------------|-----|------|-------------|
| q1_gender | 29 | categorical | Respondent gender (男/女) |
| q2_age | 30 | integer | Respondent age (years) |
| q3_education | 31 | categorical | Education level (小学及以下/初中/高中中专/大专/本科及以上) |
| q4_health | 32 | ordinal | Self-rated health (1=very poor – 5=excellent) |
| q5_marital_status | 33 | categorical | Marital status (已婚/离异/丧偶) |
| q6_is_cadre | 34 | binary | Respondent is a village cadre (0/1) |
| q7_agriculture_years | 35 | integer | Years of agricultural experience |
| q8_household_size | 36 | integer | Number of household members |
| q9_ag_labor_count | 37 | integer | Number of agricultural laborers in household |
| q10_income_level | 38 | categorical | Household annual income bracket (7 categories) |
| q11_ag_income_share | 39 | categorical | Share of income from agriculture (6 bands) |
| q12_land_mu | 40 | numeric | Cultivated land area (mu) |
| q13_operation_type | 41 | categorical | Primary farming type (粮食种植/果蔬种植/养殖/经济作物/种养结合/其他) |
| q14_join_cooperative | 42 | binary | Member of agricultural cooperative (0/1) |
| q15_stable_enterprise_link | 43 | binary | Has stable relationship with agri-enterprise (0/1) |
| q16_join_training | 44 | binary | Participated in agricultural training (0/1) |
| q17_training_times | 45 | categorical | Number of training sessions (0次/1–2次/3–4次/5次及以上) |

### Section C: Green Technology Adoption (Q18, Cols 46–66)

| Variable Name | Col | Type | Description |
|---------------|-----|------|-------------|
| q18_soil_formula_adopt | 46 | binary | Adopted soil formula fertilization (0/1) |
| q18_soil_formula_year | 47 | integer | Year of soil formula fertilization adoption |
| q18_soil_formula_2y | 48 | binary | Soil formula fertilization adopted ≥2 years (0/1) |
| q18_organic_fertilizer_adopt | 49 | binary | Adopted organic fertilizer (0/1) |
| q18_organic_fertilizer_year | 50 | integer | Year of organic fertilizer adoption |
| q18_organic_fertilizer_2y | 51 | binary | Organic fertilizer adopted ≥2 years (0/1) |
| q18_pesticide_reduction_adopt | 52 | binary | Adopted pesticide reduction technology (0/1) |
| q18_pesticide_reduction_year | 53 | integer | Year of pesticide reduction adoption |
| q18_pesticide_reduction_2y | 54 | binary | Pesticide reduction adopted ≥2 years (0/1) |
| q18_biological_control_adopt | 55 | binary | Adopted biological pest control (0/1) |
| q18_biological_control_year | 56 | integer | Year of biological control adoption |
| q18_biological_control_2y | 57 | binary | Biological control adopted ≥2 years (0/1) |
| q18_water_saving_irrigation_adopt | 58 | binary | Adopted water-saving irrigation (0/1) |
| q18_water_saving_irrigation_year | 59 | integer | Year of water-saving irrigation adoption |
| q18_water_saving_irrigation_2y | 60 | binary | Water-saving irrigation adopted ≥2 years (0/1) |
| q18_straw_return_adopt | 61 | binary | Adopted straw returning to field (0/1) |
| q18_straw_return_year | 62 | integer | Year of straw return adoption |
| q18_straw_return_2y | 63 | binary | Straw return adopted ≥2 years (0/1) |
| q18_digital_monitoring_adopt | 64 | binary | Adopted digital farm monitoring (0/1) |
| q18_digital_monitoring_year | 65 | integer | Year of digital monitoring adoption |
| q18_digital_monitoring_2y | 66 | binary | Digital monitoring adopted ≥2 years (0/1) |

### Section D: Perceptions, Digital Use & Context (Q19–Q65, Cols 67–121)

| Variable Name | Col | Type | Description |
|---------------|-----|------|-------------|
| q19_non_adopt_reason | 67 | categorical | Main reason for not adopting green technology |
| q20_green_tech_overall_effect | 68 | ordinal | Perceived overall effect of green tech (Likert) |
| q21_continue_willingness | 69 | ordinal | Willingness to continue green tech use (Likert) |
| q22_has_smartphone | 70 | binary | Owns a smartphone (0/1) |
| q23_has_stable_internet | 71 | binary | Has stable internet access (0/1) |
| q24_internet_frequency | 72 | ordinal | Frequency of internet use |
| q25_agri_info_channels | 73 | categorical | Primary agricultural information channels |
| q26_use_video_learning | 74 | binary | Uses video platforms for learning (0/1) |
| q26_use_online_consulting | 75 | binary | Uses online consulting services (0/1) |
| q26_use_online_input_purchase | 76 | binary | Purchases agricultural inputs online (0/1) |
| q26_use_online_sales | 77 | binary | Sells agricultural products online (0/1) |
| q26_use_warning_service | 78 | binary | Uses digital weather/pest warning services (0/1) |
| q26_use_digital_finance | 79 | binary | Uses digital financial services (0/1) |
| q27_online_service_frequency | 80 | ordinal | Frequency of online agricultural service use |
| q28_can_search_tech_info | 81 | ordinal | Ability to search technical info online (Likert) |
| q29_can_learn_online | 82 | ordinal | Ability to learn agricultural skills online (Likert) |
| q30_can_communicate_online | 83 | ordinal | Ability to communicate with experts online (Likert) |
| q31_can_judge_info_reliability | 84 | ordinal | Ability to judge online info reliability (Likert) |
| q32_can_buy_inputs_online | 85 | ordinal | Ability to purchase inputs online (Likert) |
| q33_info_more_convenient | 86 | ordinal | Digital tech makes info access more convenient (Likert) |
| q34_get_info_timely | 87 | ordinal | Digital tech enables timely information access (Likert) |
| q35_lower_info_cost | 88 | ordinal | Digital tech lowers information costs (Likert) |
| q36_easier_new_green_tech | 89 | ordinal | Digital tech makes learning new green tech easier (Likert) |
| q37_get_online_guidance_fast | 90 | ordinal | Can get online guidance quickly (Likert) |
| q38_loan_need | 91 | binary | Had financing need in past 3 years (0/1) |
| q39_loan_success | 92 | binary | Successfully obtained financing (0/1) |
| q40_finance_channel | 93 | categorical | Primary financing channel |
| q41_financing_affects_adoption | 94 | ordinal | Financing difficulty affects adoption decision (Likert) |
| q42_digital_finance_improves_access | 95 | ordinal | Digital finance improves credit access (Likert) |
| q43_better_credit_more_willing | 96 | ordinal | Better credit access increases adoption willingness (Likert) |
| q44_worry_yield_loss | 97 | ordinal | Worry about yield loss from green tech (Likert) |
| q45_worry_cost_increase | 98 | ordinal | Worry about cost increase from green tech (Likert) |
| q46_green_tech_increase_long_income | 99 | ordinal | Green tech increases long-term income (Likert) |
| q47_green_tech_improve_quality | 100 | ordinal | Green tech improves product quality (Likert) |
| q48_green_tech_reduce_long_risk | 101 | ordinal | Green tech reduces long-term production risk (Likert) |
| q49_green_tech_worth_investment | 102 | ordinal | Green tech is a worthwhile investment (Likert) |
| q50_platform_info_trust | 103 | ordinal | Trust in information from digital platforms (Likert) |
| q51_platform_service_reliable | 104 | ordinal | Digital platform services are reliable (Likert) |
| q52_platform_rules_fair | 105 | ordinal | Digital platform rules are fair (Likert) |
| q53_worry_data_abuse | 106 | ordinal | Worry about personal data being misused (Likert) |
| q54_unclear_data_use | 107 | ordinal | Unclear how personal data is used (Likert) |
| q55_reduce_use_for_privacy | 108 | ordinal | Would reduce platform use due to privacy concerns (Likert) |
| q56_more_willing_if_explain_data_use | 109 | ordinal | More willing to use platform if data use is explained (Likert) |
| q57_risk_preference | 110 | ordinal | Self-assessed risk preference (Likert) |
| q58_more_willing_new_method | 111 | ordinal | More willing to try new farming methods (Likert) |
| q59_know_digital_rural | 112 | binary | Aware of Digital Rural pilot policy (0/1) |
| q60_network_improved | 113 | ordinal | Network coverage improved (Likert) |
| q60_digital_service_improved | 114 | ordinal | Digital services improved (Likert) |
| q60_online_sales_info_improved | 115 | ordinal | Online sales information improved (Likert) |
| q60_gov_info_release_improved | 116 | ordinal | Government information release improved (Likert) |
| q61_gov_support_strength | 117 | ordinal | Strength of government support for green tech (Likert) |
| q62_distance_to_town_km | 118 | numeric | Distance to nearest town (km) |
| q63_biggest_difficulty | 119 | text | Open-ended: biggest difficulty in adopting green tech |
| q64_need_improve_service | 120 | text | Open-ended: services most in need of improvement |
| q65_future_concern_or_expectation | 121 | text | Open-ended: concerns or expectations for the future |

### Section E: Researcher-Constructed Variables (Cols 122–147)

| Variable Name | Col | Type | Description |
|---------------|-----|------|-------------|
| gt_soil_formula_status | 122 | categorical | Soil formula fertilization: never/partial/full adoption status |
| gt_soil_formula_area_share_band | 123 | categorical | Soil formula: share of cultivated area (banded) |
| gt_organic_fertilizer_status | 124 | categorical | Organic fertilizer adoption status |
| gt_organic_fertilizer_area_share_band | 125 | categorical | Organic fertilizer: area share (banded) |
| gt_pesticide_reduction_status | 126 | categorical | Pesticide reduction adoption status |
| gt_biological_control_status | 127 | categorical | Biological control adoption status |
| gt_biological_control_area_share_band | 128 | categorical | Biological control: area share (banded) |
| gt_water_saving_irrigation_status | 129 | categorical | Water-saving irrigation adoption status |
| gt_water_saving_irrigation_area_share_band | 130 | categorical | Water-saving irrigation: area share (banded) |
| gt_straw_return_status | 131 | categorical | Straw return adoption status |
| gt_digital_monitoring_status | 132 | categorical | Digital monitoring adoption status |
| gt_digital_monitoring_area_share_band | 133 | categorical | Digital monitoring: area share (banded) |
| gt_soil_formula_strict_adopt | 134 | binary | Soil formula: strict adoption (0/1) |
| gt_soil_formula_persist_adopt | 135 | binary | Soil formula: persistent adoption (0/1) |
| gt_organic_fertilizer_strict_adopt | 136 | binary | Organic fertilizer: strict adoption (0/1) |
| gt_organic_fertilizer_persist_adopt | 137 | binary | Organic fertilizer: persistent adoption (0/1) |
| gt_biological_control_strict_adopt | 138 | binary | Biological control: strict adoption (0/1) |
| gt_biological_control_persist_adopt | 139 | binary | Biological control: persistent adoption (0/1) |
| gt_water_saving_irrigation_strict_adopt | 140 | binary | Water-saving irrigation: strict adoption (0/1) |
| gt_water_saving_irrigation_persist_adopt | 141 | binary | Water-saving irrigation: persistent adoption (0/1) |
| gt_digital_monitoring_strict_adopt | 142 | binary | Digital monitoring: strict adoption (0/1) |
| gt_digital_monitoring_persist_adopt | 143 | binary | Digital monitoring: persistent adoption (0/1) |
| adopt_count_core | 144 | integer | Count of core green technologies adopted (0–5) |
| adopt_any_core | 145 | binary | Adopted at least one core green technology (0/1) |
| persist_count_core | 146 | integer | Count of core green technologies persistently adopted (0–5) |
| persist_any_core | 147 | binary | Persistently adopted at least one core green technology (0/1) |

---

## 6. Missing Values

Missing values appear as blank cells. Key patterns:

- **Adoption year fields** (`q18_*_year`): blank if the corresponding adopt flag = 0.
- **Persistence fields** (`q18_*_2y`): blank for technologies not adopted.
- `q39_loan_success`: blank if `q38_loan_need` = 0.
- `q40_finance_channel`: blank if `q38_loan_need` = 0.
- **Open-ended fields** (`q63`–`q65`): may be blank if respondent declined to answer.
- `hh_outlier_type`: blank if `hh_outlier_flag` = 0.

---

## 7. Data Collection

Structured face-to-face household interviews were conducted by trained enumerators. Informed consent was obtained from all participants prior to the interview. The survey instrument was pilot-tested before deployment. The variable `cadre_present` records whether a village cadre was physically present during the interview.

All data have been de-identified at the individual level. Village identifiers use coded labels (county-number format) rather than actual village names.

---

## 8. Usage Notes

- Columns 1–23 contain village- and county-level variables that are identical for all households within the same village or county. These are appropriate for multilevel or cluster-robust analyses.
- Columns 122–147 (Section E) are researcher-constructed and should be treated as derived variables, not raw survey responses. Replication of these variables from Section C data is recommended for transparency.
- The three open-ended text fields (`q63`–`q65`, cols 119–121) contain Chinese-language responses and should be processed with qualitative or NLP methods separately.
- The `hh_outlier_flag` and `hh_outlier_type` columns (cols 27–28) identify households flagged as statistical outliers. Researchers should decide independently whether to exclude these observations.
- Recommended software: Stata, R, or Python (pandas). The file can be read directly with `pd.read_excel()` or `haven::read_excel()`.

---

