# ✈️ Airline-Satisfaction-Insight

## ⚙️ Background
Our project's main objective is to predict future customer satisfaction by analyzing feedback from a specific airline, which we are referring to as Invistco Airlines for this project. We aim to determine the key factors that contribute to customer satisfaction and utilize this information to improve the experiences of neutral and dissatisfied customers.


## 📊 Data

This dataset comprises customer feedback from Invistco Airlines, including variables like passenger demographics (e.g., gender, age, and customer type) and satisfaction ratings for various service features such as seat comfort, inflight Wi-Fi, and more. It helps provide a solid foundation for in-depth analysis, exploring customer satisfaction trends, and identifying key factors influencing passenger experiences. By examining these elements, users can uncover critical insights that drive improvements in service quality and enhance decision-making for customer-centric initiatives.

Data source:

You can find the data here: https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction 


## 🏁 Getting Started

Start by setting up the appropriate environment to run a Jupyter Notebook file to ensure you have the proper versions of the required libraries. Once that is done, ensure you have PostgreSQL installed and running. You can then download the data and .ipynb file and hit "Run All" on the notebook.

The columns listed above have approximately 130K rows of data. Of these, 393 missing values are in the “Arrival Delay in Minutes” column. These are for when there is no delay in the arrival time. We have filled them with 0. We also encoded all the categorical data to numerical values.


## 🔎 Exploratory Data Analysis

1. The passenger demographics indicate a majority in the 20 to 60 age bracket, suggesting targeted services and marketing strategies for this group.
2. Female passengers slightly outnumber males.
3. Customer satisfaction levels reveal 82% loyalty, emphasizing the need for retention strategies.
4. Business class passengers show the highest satisfaction (48%), followed by economy class (45%) and economy plus class (7%).
5. Satisfaction levels are similar between genders, implying no significant differences.
6. Business travelers (69%) are more satisfied than personal travelers (31%). The age group 35-44 has the highest satisfaction (23.57%), followed by 45-54 (20.20%), highlighting areas for improvement in the youngest and oldest age groups.
7. Online boarding and inflight entertainment receive favorable ratings, indicating overall satisfaction. Departure/arrival time convenience is rated well, with most customers finding the timing acceptable.


## 💭 Predictive Modeling 

In our predictive modeling analysis, we determined that all the variables present in the data effectively predict customer satisfaction. We split the data into 60-40 training and testing splits to ensure optimal prediction. The dependent variable is 'Satisfaction,' and the rest are the independent variables.

### The models we used in this project are:
1. Logistic Classifier
2. Decision Tree Classifier
3. Bagging Classifier
4. Random Forest Classifier
5. Gradient Classifier
6. K Nearest Neighbour Classifier

We evaluated their accuracy and AUC to determine the model that consistently achieved the highest accuracy across various data subsets, helping us select the best model.

### The results are as follows:

#### Subset based on 'Type of Customer Class': 
1.  **Business Class** - Random Forest Classifier. It has an accuracy of 97.19% and an AUC mean of 99.55%.
2.  **Economy Class** - Random Forest Classifier. It has an accuracy of 94.51% and an AUC mean of 98.12%.
3.  **Economy Plus Class** - Gradient Boosting Classifier. It has an accuracy of 94.01% and an AUC mean of 98.22%.

#### Subset based on 'Gender': 
1.  **Male** - Random Forest Classifier. It has an accuracy of 95.69% and an AUC mean of 99.22%.
2.  **Female** - Random Forest Classifier. It has an accuracy of 95.85% and an AUC mean of 99.23%.

#### Subset based on 'Age Group':
1. **Age group 1 (6-18)** - Gradient Boosting Classifier. It has an accuracy of 95.23% and an AUC mean of 98.46%.
2. **Age group 2 (19-24)** - Random Forest Classifier. It has an accuracy of 94.57% and an AUC mean of 98.81%.
3. **Age group 3 (25-34)** - Random Forest Classifier. It has an accuracy of 95.69% and an AUC mean of 99.17%.
4. **Age group 4 (35-44)** - Random Forest Classifier. It has an accuracy of 94.97% and an AUC mean of 98.85%.
5. **Age group 5 (45-54)** - Random Forest ClBusiness Travel - Random Forest Classifier. It has an accuracy of 96.25% and an AUC mean of 99.37%.assifier. It has an accuracy of 95.59% and an AUC mean of 99.20%.
6. **Age group 6 (55-64)** - Gradient Boosting Classifier. It has an accuracy of 95.49% and an AUC mean of 99.19%.
7. **Age group 7 (>65)** - Gradient Boosting Classifier. It has an accuracy of 94.76% and an AUC mean of 98.25%.

#### Subset based on 'Type of Travel':
1. **Business Travel** - Random Forest Classifier. It has an accuracy of 96.25% and an AUC mean of 99.37%.
2. **Personal Travel** - Gradient Boosting Classifier. It has an accuracy of 95.80% and an AUC mean of 97.83%.

#### Subset based on 'Type of Customer':
1. **Loyal Customer** - Random Forest Classifier. It has an accuracy of 96.67% and an AUC mean of 99.46%.
2. **Disloyal Customer** - Gradient Boosting Classifier. It has an accuracy of 94.03% and an AUC mean of 98.17%.


## 📈 Business Decision

For our business decision, we selected a model for each group based on its highest accuracy. Next, we conducted recursive feature elimination to remove the weakest features. After that, we retrained the selected model for each group using the chosen features and considering both accuracy and AUC mean.

Our process involves selecting the best-performing model for each subset and identifying its top three essential features. We plan to increase the satisfaction rating by one for each of these features and predict how the initially dissatisfied passengers will be predicted as satisfied based on the test data. With model accuracies consistently above 93%, we can be confident in the accuracy of our predictions, enabling us to calculate the cost, profit, and cost-benefit of each scenario.

We assigned the profit per unit (as dissatisfied in the test, but prediction with increased satisfaction predicts satisfaction) at $500. We assigned the following costs for each variable per unit increase:
1. Flight Distance: $400
2. Inflight Wifi Service: $80
3. Ease of Online Booking: $60
4. Gate location: $140
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

The Random Forest Classifier and the Gradient Boosting Classifier emerged as the top-performing models for our selected subsets, consistently surpassing other models in accuracy and AUC. Consequently, we have used these models to inform our business decisions for the respective subsets.

Our decision performance analysis highlights that Inflight WiFi Service and Online Boarding are the most profitable features in terms of cost-benefit. Enhancements to these features could generate over $20,000 in additional revenue. Following these, Inflight Entertainment and Ease of Online Booking offer substantial benefits, with potential yields of approximately $10,000 and $3,500, respectively.

We recommend that Invistco Airlines focus on improving Inflight WiFi Service and Entertainment, as well as enhancing Online Booking and Boarding services. Allocating more budget towards these improvements is expected to boost customer satisfaction and, in turn, drive future profits and revenue growth.

<br>
<h2 align="center">Total Cost Benefit of Different Features</h2>
<p align="center">
    <img src="https://github.com/user-attachments/assets/31fbe853-4fd6-4da9-9ffa-5ef8d9221109" width="700" />
</p>
<br>

Alongside these recommendations, we suggest addressing satisfaction levels for subgroups with high dissatisfaction rates. For instance, in the eco group, over 60% of customers are dissatisfied. Tailoring services and amenities to meet the specific needs and preferences of this group could enhance their experience.

Additionally, implementing targeted retention strategies for disloyal customers could improve their satisfaction and reduce churn. Offering discounts and special deals to these customers might encourage their loyalty and foster better overall satisfaction.


## 🖍️ Limitations
1. **Lack of Additional Information**: The dataset lacked key details such as ticket price and Inflight service/food costs, which would have simplified the calculation of the business decision using actual values rather than assumptions.
2. **Categorical Satisfaction Variable**: Satisfaction was recorded as a binary categorical variable (satisfied or neutral/dissatisfied). A numerical scale (e.g., 1-10) for measuring customer satisfaction would have provided more detailed insights and allowed for a more nuanced analysis.
