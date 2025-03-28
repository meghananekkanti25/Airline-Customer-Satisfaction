# ✈️ Airline-Satisfaction-Insight

## ⚙️ Background
Our project's main objective is to predict future customer satisfaction by analyzing feedback from a specific airline, which we are referring to as Invistco Airlines for this project. We aim to determine the key factors contributing to customer satisfaction and utilize this information to improve the experiences of neutral and dissatisfied customers.

## 📊 Data
This dataset includes customer feedback from Invistco Airlines, with variables such as passenger demographics (e.g., gender, age, customer type) and satisfaction ratings for various service features like seat comfort, inflight Wi-Fi, and more. This dataset provides a solid base for detailed analysis, helping to uncover trends in customer satisfaction and identify areas for improvement. By exploring these factors, we can enhance service quality and make better decisions to meet customer needs.

Data source: [Airline Passenger Satisfaction Dataset](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction)

## 🏁 Getting Started
To begin, set up the appropriate environment to run a Jupyter Notebook and ensure you have the required library versions. After that, make sure PostgreSQL is installed and running. Then, download the data and the .ipynb file and click "Run All" to start the analysis.

The dataset contains about 130K rows, with 393 missing values in the "Arrival Delay in Minutes" column. These missing values were filled with 0, assuming no delay for these cases. We also encoded the categorical variables as numerical values for analysis.

## 🔎 Exploratory Data Analysis
1. The majority of passengers are in the 20-60 age range, suggesting that services and marketing strategies should be tailored to this demographic.
2. There are slightly more female passengers than male passengers.
3. 82% of passengers are loyal, indicating a strong customer base that requires attention to maintain retention.
4. Business class passengers report the highest satisfaction (48%), followed by economy class (45%) and economy plus (7%).
5. Satisfaction levels are similar between genders, meaning there are no significant differences based on gender.
6. Business travelers (69%) tend to be more satisfied than personal travelers (31%). The age group 35-44 has the highest satisfaction (23.57%), followed by 45-54 (20.20%). This suggests a need for improvement in the youngest and oldest age groups.
7. Passengers rated online boarding and inflight entertainment favorably, indicating general satisfaction with these features.
8. Departure/arrival time convenience is also rated well, with most passengers finding the timing acceptable.

## 💭 Predictive Modeling 
In the predictive modeling phase, we found that all variables in the dataset contribute to predicting customer satisfaction. We split the data into a 60-40 training and testing split, with 'Satisfaction' as the dependent variable and all other variables as independent.

### The models we used in this project are:
1. Logistic Classifier
2. Decision Tree Classifier
3. Bagging Classifier
4. Random Forest Classifier
5. Gradient Classifier
6. K Nearest Neighbour Classifier

We evaluated the models based on accuracy and AUC to determine which consistently performed the best.

### Results:

#### Subset based on 'Type of Customer Class': 
1.  **Business Class** - Random Forest Classifier with an accuracy of 97.19% and an AUC mean of 99.55%.
2.  **Economy Class** -  Random Forest Classifier with an accuracy of 94.51% and an AUC mean of 98.12%.
3.  **Economy Plus Class** - Gradient Boosting Classifier with an accuracy of 94.01% and an AUC mean of 98.22%.

#### Subset based on 'Gender': 
1.  **Male** - Random Forest Classifier with an accuracy of 95.69% and an AUC mean of 99.22%.
2.  **Female** - Random Forest Classifier with an accuracy of 95.85% and an AUC mean of 99.23%.

#### Subset based on 'Age Group':
1. **Age group 1 (6-18)** - Gradient Boosting Classifier with an accuracy of 95.23% and an AUC mean of 98.46%.
2. **Age group 2 (19-24)** - Random Forest Classifier with an accuracy of 94.57% and an AUC mean of 98.81%.
3. **Age group 3 (25-34)** - Random Forest Classifier with an accuracy of 95.69% and an AUC mean of 99.17%.
4. **Age group 4 (35-44)** - Random Forest Classifier with an accuracy of 94.97% and an AUC mean of 98.85%.
5. **Age group 5 (45-54)** - Random Forest Classifier with an accuracy of 96.25% and an AUC mean of 99.37%.
6. **Age group 6 (55-64)** - Gradient Boosting Classifier with an accuracy of 95.49% and an AUC mean of 99.19%.
7. **Age group 7 (>65)** - Gradient Boosting Classifier with an accuracy of 94.76% and an AUC mean of 98.25%.

#### Subset based on 'Type of Travel':
1. **Business Travel** - Random Forest Classifier with an accuracy of 96.25% and an AUC mean of 99.37%.
2. **Personal Travel** - Gradient Boosting Classifier with an accuracy of 95.80% and an AUC mean of 97.83%.

#### Subset based on 'Type of Customer':
1. **Loyal Customer** - Random Forest Classifier with an accuracy of 96.67% and an AUC mean of 99.46%.
2. **Disloyal Customer** - Gradient Boosting Classifier with an accuracy of 94.03% and an AUC mean of 98.17%.

## 📈 Business Decision
We selected the best-performing model for each subset based on accuracy. Afterward, we performed recursive feature elimination to discard the weakest features. We then retrained the selected models using the chosen features, considering both accuracy and AUC mean.

By selecting the highest-performing models for each group and identifying their top three features, we aimed to improve satisfaction by increasing these features' ratings by one point for each group. We then predicted how dissatisfied passengers would respond to these changes based on the test data. With model accuracies consistently above 93%, we can confidently rely on these predictions, allowing us to calculate the costs, profits, and cost-benefit for each scenario.

We assigned a profit per unit (for those initially dissatisfied but predicted to be satisfied with increased satisfaction) at $500. We also determined the cost for each feature per unit increase:

1. Flight Distance: $400
2. Inflight Wi-Fi Service: $80
3. Ease of Online Booking: $60
4. Gate Location: $140
5. Food and Drink: $100
6. Online Boarding: $70
7. Seat Comfort: $110
8. Inflight Entertainment: $50
9. On-board Service: $30
10. Leg-room Service: $500 (Bigger plane impractical)
11. Baggage Handling: $20
12. Check-in Service: $20
13. Inflight Service: $40
14. Cleanliness: $20

## 🔖 Takeaway and Next Steps

The Random Forest and Gradient Boosting Classifiers emerged as the most accurate models for each subset, consistently outperforming others in terms of accuracy and AUC. We used these models to guide our business decisions for each group.

Our analysis highlights that improvements to Inflight Wi-Fi Service and Online Boarding offer the greatest cost-benefit, with the potential to generate over $20,000 in additional revenue. Inflight Entertainment and Ease of Online Booking are also valuable, offering benefits of about $10,000 and $3,500, respectively.

We recommend that Invistco Airlines prioritize enhancements to Inflight Wi-Fi, Entertainment, and Online Booking/Boarding services. Allocating more resources to these areas should help increase customer satisfaction and lead to higher profits.

<br>
<h2 align="center">Total Cost Benefit of Different Features</h2>
<p align="center">
    <img src="https://github.com/user-attachments/assets/31fbe853-4fd6-4da9-9ffa-5ef8d9221109" width="700" />
</p>
<br>

In addition to these recommendations, we suggest focusing on passengers who are highly dissatisfied, particularly in the economy class, where over 60% are dissatisfied. Tailoring services to their needs could improve their experience.

Furthermore, targeted retention strategies for disloyal customers could help increase their satisfaction and reduce churn. Offering special deals and discounts to these customers could boost loyalty and overall satisfaction.


## 🖍️ Limitations
1. **Lack of Additional Information**: The dataset did not include details like ticket prices or costs for inflight services/food, making it harder to calculate the business decision using actual values instead of assumptions.
2. **Categorical Satisfaction Variable**: Satisfaction was recorded as a binary categorical variable (satisfied or neutral/dissatisfied). A numerical scale (e.g., 1-10) would have provided more granular insights and allowed for a more detailed analysis.



