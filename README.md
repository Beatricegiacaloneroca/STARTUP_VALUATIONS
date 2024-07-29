# Impact of Founding Date on Startup Valuation

<img width="440" alt="Screenshot 2024-07-29 at 4 24 38 PM" src="https://github.com/user-attachments/assets/7723bd81-2ed7-4b30-90d8-0b391f4695fc">

## Introduction
This project explores the relationship between the founding dates of startups and their subsequent valuations. We aim to understand how economic cycles influence startup success rates and provide insights for investors and entrepreneurs.

## Data Source
We analyze a dataset of startups founded between 2011 and 2021, detailing their valuations, founding dates, and other relevant data.

## Methodology
The analysis employs Ordinary Least Squares (OLS) Regression to quantify the effect of founding dates on startup valuations. Data preprocessing steps include cleaning, handling missing values, and preparing variables for regression analysis.

## Exploratory Data Analysis (EDA)
Our initial exploration focuses on understanding the distribution of startup valuations:

* We observe that in the VC industry, the Power Law Curve defines valuations where few startups get most of the value
<img width="323" alt="Screenshot 2024-07-29 at 4 46 14 PM" src="https://github.com/user-attachments/assets/0fb0baed-b7b4-4850-8e62-4c1e476b43c0">

* The countries and cities where there are more startups are in the US, followed by China
<img width="859" alt="Screenshot 2024-07-29 at 4 47 31 PM" src="https://github.com/user-attachments/assets/aa07bb44-5cc1-4bfc-9ec4-74a3e1b68cb2">

* As expected AI is the industry where mean valuations are higher, however, fintech is the most crowded one
<img width="368" alt="Screenshot 2024-07-29 at 4 47 50 PM" src="https://github.com/user-attachments/assets/066b2be9-54f4-4088-8c0d-c54771cc99bf">


Now that we have some context of the overall industry, we proceed to understand what is driving this valuations and whether or not the date when a startup was founded is a significant indicator of its valuation.
## Regression Analysis
* We have primarily focused on mitigating the influence of quantitative confounders to understand the relationship between the year a startup joined and its valuation.
  * Quantitative confounders are variables that could potentially impact both the independent variable (Join Date) and the dependent variable (Valuation).
  * By employing linear regression and incorporating additional quantitative variables such as encoded categorical features (City_encoded, Investor_encoded, Country_encoded, and Industry_encoded), we aim to control for these confounders.
  * 
      <img width="471" alt="Screenshot 2024-07-29 at 4 36 49 PM" src="https://github.com/user-attachments/assets/cd62573a-07d4-4a4f-b5f2-cbd1a0098282">
* **Results of OLS**:
  
  <img width="528" alt="Screenshot 2024-07-29 at 4 41 37 PM" src="https://github.com/user-attachments/assets/1fd26e65-2846-4b04-9fa8-d88af27bae89">

    * **R squared**
        * A low R-squared value (0.044 in this case) indicates that the model, as a whole, explains only about 4.4% of the variability in startup valuations.
        * This might suggest that other unmodeled factors or inherent variability in startup valuations are not captured by the variables included in the model.
        * In economics and business-related models, it is common to encounter low R-squared values because these fields are influenced by many unobserved factors (like market conditions, unmeasured entrepreneurial skills, technological advancements, etc.).
    * **The impact of join date**
      * Despite the overall model not explaining a large portion of the variance in startup valuations, **there is strong evidence that the year in which a startup is founded has a significant linear relationship with its valuation.**
      * The negative coefficient of -0.8258 implies **that each additional year later a startup is founded, its valuation tends to decrease, holding all other factors constant**.
      * However, it's crucial to interpret this result in the context of the conclusion that the relationship between founding year and valuation is influenced by cyclical economic factors.
      * **During the years 2016-2021**, there appears to be a negative association, **but this may change in subsequent economic cycles.**
    * **Remaining Coefficents**
        * The coefficients for "City_encoded," "Investor_encoded," "Country_encoded," and "Industry_encoded" do not show strong statistical significance (p > 0.05), suggesting that these variables may not have a substantial impact on valuations after accounting for the founding year.


## Conclusion
Overall, while the analysis demonstrates that the founding year does explain a portion of the variance in startup valuations, the modest R-squared value and the potential influence of unmeasured qualitative confounders indicate that other factors, not included in this model, play a significant role in determining startup valuations.

Reach out to beatricegiacaloneroca@gmail.com for additional questions!

