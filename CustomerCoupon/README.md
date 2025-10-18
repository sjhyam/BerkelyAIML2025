# Coupon Acceptance Analysis: Bar and Restaurant(<20) Coupons

## Overview
This repository presents an analysis of coupon acceptance from the UCI Driving Coupon dataset (n=12,564 total observations). Focus is on two coupon types: **Bar coupons** (n=2,017; 41.00% acceptance rate, 827 acceptors vs. 1,190 rejectors) and **Restaurant(<20) coupons** (n=2,786; 70.71% acceptance rate, 1,970 acceptors vs. 816 rejectors). High acceptance for cheap restaurants indicates broad appeal for value-driven meals, while bars show selectivity, likely due to social/contextual factors.

Analysis uses Python (pandas for summaries, seaborn/matplotlib for visualizations) to highlight differences in demographics, lifestyle, and socioeconomic traits. Insights suggest targeted marketing—e.g., young social singles for bars, budget-conscious youth for cheap eats.

**Data Source**: UCI Machine Learning Repository (survey on driving scenarios and coupon acceptance). [Dataset Link](https://archive.ics.uci.edu/dataset/367/online+retail)

**Tools Used**:
- Python 3.x with pandas, seaborn, matplotlib
- Jupyter Notebook: `coupon_analysis.ipynb` (includes full code and plots)

## Key Statistical Differences
Statistical summaries (via `value_counts(normalize=True)`) show top proportions (%) for acceptors (Y=1) vs. rejectors (Y=0). Acceptors for both skew younger, more social, and slightly lower-income; bar acceptors are more male/single, while restaurant acceptors are balanced but more child-free.

### Bar Coupons
| Category          | Acceptors (Top Proportions)                  | Rejectors (Top Proportions)                  | Key Insight |
|-------------------|----------------------------------------------|----------------------------------------------|-------------|
| **Age**          | 21 (25.5%), 26 (23.3%), 31 (15.1%)          | 31 (18.0%), 21 (17.3%), 26 (17.0%)          | Acceptors younger (peak 20s); rejectors older/more even. |
| **Gender**       | Male (57.0%), Female (43.0%)                | Female (57.9%), Male (42.1%)                | Acceptors skew male. |
| **Passenger**    | Alone (59.1%), Friend(s) (22.7%), Partner (12.9%) | Alone (59.7%), Partner (14.0%), Kid(s) (13.7%) | Acceptors more with friends; rejectors with kids. |
| **Marital Status**| Single (43.7%), Married (35.1%), Unmarried Partner (18.3%) | Married (49.7%), Single (25.2%), Unmarried Partner (19.1%) | Acceptors more single. |
| **Income**       | $25K-$37K (17.3%), $100K+ (16.7%), $12K-$25K (14.5%) | $25K-$37K (14.7%), $37K-$50K (14.6%), $12K-$25K (14.1%) | Similar spread; acceptors slightly lower mean ($52K vs. $53K). |
| **Occupation**   | Student (14.5%), Unemployed (11.0%), Computer/Math (10.5%) | Unemployed (17.6%), Computer/Math (12.2%), Student (11.0%) | Acceptors more students; rejectors unemployed. |
| **Has Children** | No (68.3%), Yes (31.7%)                    | Yes (51.5%), No (48.5%)                    | Acceptors mostly child-free. |

### Restaurant(<20) Coupons
| Category          | Acceptors (Top Proportions)                  | Rejectors (Top Proportions)                  | Key Insight |
|-------------------|----------------------------------------------|----------------------------------------------|-------------|
| **Age**          | 21 (21.4%), 26 (20.8%), 31 (16.0%)          | 26 (18.5%), 21 (18.0%), 50+ (17.4%)         | Acceptors peak in 20s; rejectors more 50+. |
| **Gender**       | Female (50.3%), Male (49.7%)                | Female (52.8%), Male (47.2%)                | Balanced; slight female tilt in rejectors. |
| **Passenger**    | Alone (46.5%), Friend(s) (33.6%), Partner (10.1%) | Alone (63.6%), Friend(s) (20.1%), Kid(s) (9.1%) | Acceptors more social; rejectors solitary. |
| **Marital Status**| Married (39.2%), Single (38.7%), Unmarried Partner (17.5%) | Married (42.5%), Single (34.6%), Unmarried Partner (15.9%) | Acceptors more single/unmarried. |
| **Income**       | $25K-$37K (17.1%), $50K-$62K (14.1%), $12K-$25K (13.9%) | $37K-$50K (15.4%), $12K-$25K (15.4%), $25K-$37K (13.5%) | Acceptors lower mean ($51K vs. $54K). |
| **Occupation**   | Unemployed (13.9%), Student (12.5%), Computer/Math (10.8%) | Unemployed (16.8%), Student (12.1%), Computer/Math (10.8%) | Acceptors favor tech/sales/education. |
| **Has Children** | No (59.3%), Yes (40.7%)                    | No (57.2%), Yes (42.8%)                    | Slight child-free edge for acceptors. |

## Visualizations
Visualizations (generated in `coupon_analysis.ipynb`) highlight differences: Subplots for demographics (age/gender/passenger/marital), boxplots for income (mapped numeric), histograms for temperature, and horizontal bars for occupations (top-5). Plots include legible labels, titles, and scaling (e.g., top-5 limits, rotations). Key patterns: Youth/social skew in acceptors for both; bars show stronger male/single peaks.

- **Demographics Subplots**: Bars emphasize male/young social acceptors (peaks at 21/26). Restaurants: Balanced but younger/social.  
  *(Images: `demographics_bar.png`, `demographics_restaurant.png`)*

- **Income Boxplots**: Both show lower medians for acceptors (~$50K vs. $53K-$54K), fewer high earners.  
  *(Images: `income_bar.png`, `income_restaurant.png`)*

- **Temperature Histograms**: Minimal differences; acceptance stable across 30°F-80°F.  
  *(Images: `temperature_bar.png`, `temperature_restaurant.png`)*

- **Occupations Bars**: Bars: Students prominent in acceptors. Restaurants: Unemployed/students lead, but acceptors more diverse.  
  *(Images: `occupations_bar.png`, `occupations_restaurant.png`)*

## Conclusion
**Bar Coupons**: Acceptors (41% rate) are young (20s), male, single, child-free socializers (alone/friends) with student/unemployed profiles—ideal for nightlife incentives. Rejectors: Older, family-oriented professionals. Target: Urban young adults via friend-focused ads.

**Restaurant(<20) Coupons**: Acceptors (71% rate) are 20s youth, balanced gender, social/child-free, lower-income students/tech workers—value-seekers for casual eats. Rejectors: Older, solitary higher-earners. Target: Budget youth with solo/group deals.

These patterns (e.g., youth/social skew) align with survey context (e.g., passengers, time/weather minimal impact). Further steps: Logistic regression for prediction; expand to other coupon types.

## Setup Instructions
1. Clone the repo: `git clone https://github.com/sjhyam/BerkelyAIML2025.git CustomerCoupon'
2. Install dependencies: `pip install pandas seaborn matplotlib`
3. Run the notebook: `jupyter notebook coupon_analysis.ipynb`
4. View plots: Generated PNGs saved in `/images/`.

## License
MIT License. See [LICENSE](LICENSE) for details.

---