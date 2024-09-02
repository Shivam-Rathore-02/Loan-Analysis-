# Customer Assistance Analysis

## Project Overview

This project aims to calculate and analyze the total assistance provided to families based on their socio-economic status, household items, family size, and residence type. The assistance is calculated using a set of predefined rules and deductions as detailed below.

## Dataset Description

The dataset used in this analysis contains the following columns:

- **S/No**: Serial number of the entry.
- **Location Category**: The location of the family, categorized as A, B, or C.
- **Refrigerator**: Indicator whether the family owns a refrigerator (Yes/No).
- **Television**: Indicator whether the family owns a television (Yes/No).
- **Family Size**: The number of members in the family.
- **Residence Type**: Type of residence (Owned, Rented, Homeless).
- **Annual Family Income**: The total annual income of the family.
- **Base Assistance %**: The percentage of base assistance the family is eligible for, based on their income and location.
- **Base Assistance**: The calculated base assistance amount.
- **Eligible Deduction**: The total percentage of deductions applicable to the family based on their possessions and family size.
- **Deduction Amount**: The total deduction amount subtracted from the base assistance.
- **Additional Support**: The additional support amount based on the type of residence.
- **Total Assistance**: The final assistance amount provided to the family after all deductions and additions.

## Calculation Logic

### Base Assistance
Base assistance is determined by the family's location category and their per person income. The assistance percentage decreases as income increases, and the exact percentage is based on the following table:

| Per Person Income Above | A   | B   | C   |
|-------------------------|-----|-----|-----|
| 0                       | 25% | 20% | 15% |
| 10,000                  | 20% | 15% | 10% |
| 100,000                 | 12% | 10% | 8%  |
| 200,000                 | 0%  | 5%  | 7%  |

### Deductions on Base Assistance
Deductions are applied to the base assistance based on the following criteria:

- **Refrigerator**: 50% deduction if the family owns a refrigerator.
- **Television**: 40% deduction if the family owns a television.
- **Family Size > 5**: 30% deduction if the family size exceeds 5 members.

The maximum deduction cannot exceed the base assistance amount.

### Additional Support
Additional support is provided based on the family's type of residence:

- **Owned**: No additional support.
- **Rented**: $5,000 additional support.
- **Homeless**: $10,000 additional support.

### Total Assistance Calculation
The total assistance is calculated as follows:

1. **Determine Base Assistance**: Calculate the base assistance using the income and location.
2. **Apply Deductions**: Calculate the total deductions based on the family's possessions and size. Ensure that deductions do not exceed the base assistance.
3. **Add Additional Support**: Add the additional support based on the type of residence.
4. **Final Total Assistance**: Subtract the deductions from the base assistance and add the additional support.

### Summary Statistics
The following statistics are calculated for each location category:

- **% Families with Refrigerator**: The percentage of families in each location that own a refrigerator.
- **% Families with Television**: The percentage of families in each location that own a television.
- **Total Assistance**: The total assistance provided to all families in each location.
- **Average Assistance per Family**: The average assistance provided to each family in the location.
- **Average Assistance per Person**: The average assistance per person in each location.

## Example Results
Based on the dataset, the results might include something like:

- **Location A**:
  - 56.43% of families own a refrigerator.
  - Average assistance per family: `$X`.
  - Average assistance per person: `$Y`.

## Conclusion
This analysis helps in understanding how assistance is distributed among families based on their socio-economic status and provides insights into where additional support might be needed.

## Future Work
Future improvements could include:

- Incorporating more factors into the assistance calculation, such as health conditions or educational expenses.
- Analyzing the impact of this assistance on family well-being.

---

