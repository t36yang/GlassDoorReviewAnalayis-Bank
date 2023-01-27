# Glassdoor Review Analayis-Citi Bank

![Glassdoor-Logo](https://user-images.githubusercontent.com/117051182/215185275-eb20a3a0-4209-49d3-9f8c-cecd23e9e14e.png)

# OVERVIEW #
This data analysis report examines employee reviews and scores on Glassdoor for Citi Bank. By using NLP algorithms, the project aims to process and analyze the employee reviews to identify the main themes discussed among employees. The goal of the project is to provide Citi leaders with insights to maintain a high score (4-5) on Glassdoor by building a prediction model to estimate future Glassdoor rating changes.

### Why is Glassdoor score important to employers? ###
For employers, a high Glassdoor score can have a positive impact on both job seekers and business consumers.

For job seekers, Glassdoor reviews provide valuable information about the company culture and can influence their decision to apply for a job. A high Glassdoor score can attract more qualified candidates, making the recruiting process more efficient.

For business consumers, Glassdoor reviews can impact their perception of the company's reputation, credibility, and profitability. Positive reviews can lead to more business and increased consumer trust, while negative reviews can have the opposite effect. A high Glassdoor score can be beneficial for companies looking to attract new customers and retain existing ones.

Overall, Glassdoor reviews can have a significant impact on a company's ability to attract and retain employees, as well as its reputation and profitability. Employers should take the time to monitor their company's Glassdoor score and take steps to improve it if necessary.

## PROBLEM STATEMENT ##
By the end of this analysis, the following problems will be addressed:
What do employees say about Citi?
* Displaying major themes, keywords, and topics from the Glassdoor reviews.
What are the trends of employee reviews?
* Graphs displayed later on will describe the trend of employee reviews by year.
What is the Glassdoor score for the upcoming year?
* A prediction model will be built to forecast future rating scores.
What can Citi do to improve?
* Recommendations will be provided to Citi based on the feedback information.

## DATASET ##
The initial dataset used for this analysis was scraped from Glassdoor.com for US locations only. The dataset includes information such as the review title, pros, cons, and date-title. In total, there were more than 25,000 reviews captured. Because the data was scraped and unstructured, regular expressions were used to clean it by removing punctuation, special characters, and frequently used words such as Citi and Citibank. Missing data and reviews from reviewers who had less than five words were dropped from the dataset. To improve prediction and interpretation, the targets (Glassdoor scores) were separated into two groups, 1-3 and 4-5, for model training purposes.

## EXPLORATORY DATA ANALYSIS ##

#### Trend of the glassdoor ratings by year ####

Trend of ratings

![rating trend by year](https://user-images.githubusercontent.com/117051182/215186451-27f9f394-cdf8-4eef-a36a-9f007574a38f.png)


Number of reviews per year

![rating distrbution by year](https://user-images.githubusercontent.com/117051182/215186516-8901de21-8881-4bf7-b647-d2dd15d0151c.png)


Insight: The trend of Glassdoor review scores from 2008 to 2022 shows an upward trend. There were more reviews starting from 2016. The dispersion in the line chart was wide between 2008 and 2015 as there were fewer reviewers back then. However, the dispersion begins to decrease after 2016 as the number of reviewers increases. It's also important to note that following the 2008 financial crisis, the Glassdoor review scores decreased, but began to increase again afterwards.

#### Distribution of rating scores ####

![rating count ](https://user-images.githubusercontent.com/117051182/215186664-629ec07b-0c4f-417b-ba75-f6f1e36de0f2.png)

The majority of employees rated 4.0 or 3.0 on Glassdoor, which aligns with the current overall score of 3.9.

#### NLP Analysis of Keywords and Topics ####

Following the application of a Natural Language Processing algorithm, five topics were identified from both Pro and Cons feedback. 
Below are the key words for each of the five topics extracted from the employee reviews of pros.

The top five topics for positive feedbacks are: 
* Work life balance
* Learning opportunities
* Benefit pay
* Flexible work environment
* Nice smart people (good culture)

![keywords - Pros](https://user-images.githubusercontent.com/117051182/215186974-bf2484aa-cc70-4f7a-b186-4731540b72c3.png)

Below are the key words for each topic extracted from the employee reviews of cons.

![keywords for Cons](https://user-images.githubusercontent.com/117051182/215187396-eb31b348-45c3-4f62-8635-033dc3d236a2.png)

The top five topics for negative feedbacks are: 
* Work pressure
* Tight deadline
* Long work hours
* Low bonus salary
* Lack management

The frequency of each topic mentioned in the reviews: 

![pros vertical](https://user-images.githubusercontent.com/117051182/215187569-a49d7f32-9c90-48f4-acd5-bb2962a41a58.png)           ![vertical cons](https://user-images.githubusercontent.com/117051182/215187623-eaea38ee-ec06-413f-86dc-e6f0d9337cc7.png)

Insight: As the two charts represent, Citi has great opportunities for learning, great benefits, and a flexible work environment. However, some employees also suggested that they experienced tight deadlines and poor management.

## PREDICTION MODEL ##

In order to produce a prediction model for forecast glassdoor rating, a baseline model was created based on the result of five machine learning algorithms on a training set. 

See below for a summary:

![Screen Shot 2023-01-27 at 3 15 42 PM](https://user-images.githubusercontent.com/117051182/215188725-83880cf9-0d03-4e7c-840d-292386783efc.png)

Boxplot:

![algorithm graph](https://user-images.githubusercontent.com/117051182/215188870-31f5f0ed-82c2-40da-aa62-b408f478f455.png)

Random Forest and Decision Tree had the highest overall score. The prediction modeling will be focused on these two.

After tuning and training on the test set, Random Forest model had the best result - 70% of accuracy. 

![confusion matrix](https://user-images.githubusercontent.com/117051182/215189181-c183d285-6eaf-4eb4-bf1a-3036342faba0.png)

Out of 3301 test samples, this model has been trained to accurately predict 70% of reviews to give an accurate Glassdoor score.

Accuracy Score: 0.70 Precision Score: 0.70 Recall Score: 0.71 F1 Score: 0.70 Type 1 error: 16% Type 2 error: 15%

#### Topic Importance in Prediction Model ####

From the prediction model, below are the topics that influence the glassdoor score the most:
Poor Management, Work life balance/tight deadline/long work hours, Culture (nice/smart people), Bonus

![feature importance](https://user-images.githubusercontent.com/117051182/215189426-9e8bf1c0-2c7b-4655-8c99-bed8f3f26295.png)

## RECOMMENDATION ##

Based on the insights drawn from previous data analysis, I would like propose the following recommendations: 

* Conduct in-depth research over the topics of management and work hours (tight deadline): design a research project to gather more feedback on the details about the topic from employees. Identify the hypotheses, sample group and research method to extract the key information from employees.  
* Managerial training: Once the causes of the issues are identified, review management training material and revise the training material accordingly to tackle the issues. 
* Work stress- Explore benefits programs and options for reducing stress for employees. Conduct further research within the company over workload assignment.
* Research over Bonus Benchmark - Compare bonus payment with other companies in the industry.

## NEXT STEPS ##
* Benchmark Comparison - conduct a competitor analysis to study the reviews of other companies. 
* Sentiment Analysis - Conduct unsupervised machine learning methods to conduct analysis over employees sentiment.
* Survey - design and send out surveys to employees to gather real time pros/cons feedback to fit into the prediction model and to review the score of the current employees. 
* Arrange Annual Feedback Analysis - Set up regular analysis to capture employees' glassdoor review feedback.
