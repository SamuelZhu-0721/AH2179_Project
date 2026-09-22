

# 🔨 Project option 2 - traffic

#### **Final Project Assignment Option 1: Traffic flow short-term prediction**

(Note that you only need to choose ONE and ONLY ONE option for your final project assignment.)

#### **Project Description** 

Trafikverket (TRV) is looking to using clustering and AI for short-term prediction application. The TRV selected a test bottleneck in Stockholm (MCS data) as "Proof of Concept" (POC) consisting of interchange between the Pampas exit and the Hornsberg exit, see Figure below. 

![case_study_visualization](/Users/samuel/Downloads/case_study_visualization.png)

The starting point for the short-term prediction is data from MCS/TDIS for the current situation, which are used to calculate the current situation and the predicted situation in 15 minutes, 30 minutes, and 60 minutes. The premise is to use clustering or AI with historical data updating prediction every minute. 

Short-term prediction is essential for data-driven Traffic Management and evolving from re-active to pro-active traffic management. Trafik Stockholm and TRV are investing in understanding better highway traffic and how incidents and planned work impact mobility in affected urban areas using data-driven and AI approaches. To the best of our knowledge, this is the first dataset benchmark prepared and decided by TRV that should enable cross-model, industry and research comparison for short-term prediction applications. 

In this project, you will be working on building machine learning models that predict in real-time (each minute) the flow or average speed for the future 15 minutes. Your model should be trained and validated for the morning peak period 07:30 – 08:30. Thus at 7:00, predict flow for 7:01-7:16, at 7:02, predict flow for 7:02-7:17. Note that you can use prior past intervals before 07:30. 

*Notes:* 

- You may or may not consider splitting the dataset in space and time using clustering for producing sub-datasets that can constitute a better bias-variance mix for training your prediction models. For example – grouping the sensors, portals or days.
- Furthermore, for model performance and computational reasons, you can consider aggregating 1-minute historical periods to larger 5 or 15 minute datasets which may or may not have positive impacts on computational complexity and your model.
- Note that 1-minute intervals can contain a lot of zeros or missing values, aggregating to longer intervals can be good for your models. Please investigate before, to motivate the decision. You can also consider imputation of missing data.

There are two datasets provided, first for training and second for evaluation. Note that the evaluation dataset should not be a part of the training. Training dataset can be split into training and testing datasets according to your design. Please also note that you do not have to use a complete training dataset, and you can choose a sub-set. Anyway, at the end, you should provide a prediction performance of your final selected model using a complete evaluation dataset. This dataset shows how your model performs in the application. The final evaluation of your model should be done on the provided evaluation dataset for period 07:30-08:30 each minute for the coming 15-minute interval; thus, at 7:02, predict flow for 7:02-7:17. 

#### **Dataset** 

! The tutorial's dataset is not open-sourced; you are only allowed to use it during this course, and you are not allowed to make it publicly available on GitHub or other platforms.

You are provided with a training dataset containing historical information about the speed and number of vehicles passing the MCS sensors each minute during 2021-06-01 – 2021-12-31. It is up to you which days and how you split this dataset for training and calibration of your model. Additionally, you will receive a test/final evaluation dataset from 2022-01-01 – 2022-06-30 that cannot be part of the model's training. On this independent dataset from training, you will show your model's performance. 

You can download the dataset from this link [dataset_for_traffic_project_assignment.zip](https://canvas.kth.se/courses/64980/files/10498400?wrap=1)[Download dataset_for_traffic_project_assignment.zip](https://canvas.kth.se/courses/64980/files/10498400/download?download_frd=1) and dataset description [traffic_project_assignment_dataset_description.pdf](https://canvas.kth.se/courses/64980/files/10498413?wrap=1)[Download traffic_project_assignment_dataset_description.pdf](https://canvas.kth.se/courses/64980/files/10498413/download?download_frd=1).

In case of interest, we also give you an option beyond the Trafikverket benchmark case study, not limiting you to the morning peak; you may consider the complete all-day long dataset from 00:00:00 to 23:59:59 for training and evaluating your prediction models, you can find it by this link: [dataset_for_traffic_project_assignment_ALLday.zip](https://canvas.kth.se/courses/64980/files/10498439?wrap=1)[Download dataset_for_traffic_project_assignment_ALLday.zip](https://canvas.kth.se/courses/64980/files/10498439/download?download_frd=1)

The datasets include these features: 

- DP_ID - ID of sensor at the portal location
- PORTAL - ID of portal
- Date - Date format YYYYmmdd
- Time - Time format HH:MM:SS
- Interval_1 - Index, interval 0: 00:00:00 – 00:00:59; 1: 00:00:01 – 00:01:59
- Interval_5 - Index, interval 0: 00:00:00 – 00:04:59; 1: 00:05:00 – 00:09:59
- Interval_15 - Index, interval 0: 00:00:00 – 00:14:59; 1: 00:15:00 – 00:29:59
- Interval_30 - Index, interval 0: 00:00:00 – 00:29:59; 1: 00:30:00 – 00:59:59
- Interval_60 - Index, interval 0: 00:00:00 – 00:59:59; 1: 01:00:00 – 01:59:59
- SPEED_MS_AVG - Average recorded speed from all the observations during 1-minute interval, in meters per second
- FLOW - The number of observed vehicles during 1-minute interval

#### **Tasks** 

*A. Descriptive analysis*  

Analyze the sensor data and understand the flow or speed patterns in both time and space (e.g., using descriptive statistics, graphs, and histograms).  

*B. Problem formulation*  

Formulate your speed or flow prediction problem and justify it by discussing its reasonableness for practical use in real-time application. For example,  

1. What to predict? – Do you predict flow, speeds, or both?
2. What is the problem type? – Formulate as a clustering problem, a regression problem, a classification problem, or a combination of these? 
3. What features to use? - Develop a-priori hypotheses about features you think are important in predicting 15, 30, 60 minutes in the future. 


*C. Model development* 

1. Data Preprocessing: Clean and preprocess the dataset if necessary, data normalization, and converting categorical variables into suitable formats for modeling.
2. Feature Engineering: Analyze the dataset to identify relevant features that could impact bus arrival times. Create new features if necessary, such as time-based features, distance-related features, and aggregation of historical data.
3. Exploratory Data Analysis (EDA): Perform EDA to gain insights into the relationships between different variables and bus arrival times. Visualize patterns, correlations, and outliers in the data.
4. Model Selection: Select appropriate machine learning algorithms for short-term prediction task. Consider conventional machine learning models or deep neural network models depending on the nature of the data. 
5. Model Training: Split the dataset into training and validation sets. Train the selected models using the training data and fine-tune hyperparameters to achieve optimal performance.
6. Model Evaluation: Evaluate the trained models using appropriate evaluation metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and Mean Absolute Percentage Error (MAPE). Compare the performance of different models to select the best-performing one. For a comparative analysis, you need to develop at least three different types of models. 

*D. Model diagnostics*  

Design different scenarios to explore how the best model works overall. When and where it does not work? Is it robust to noisy and missing data in real-time? Is it generalizable over months?  

*E. Model deployment*  

Would you recommend your model to the agency to use?  Reflect on what you learned in the project and what you envision as an innovative way to operationalize it in practice.  

*F. Report* 

Put your code with comments on your GitHub repository and save your best-trained model to an external file (.keras format, https://keras.io/api/saving/model_saving_and_loading/).

Submit a report that addresses tasks A) to E) and answers all questions, including the following:

- Brief introduction and project objectives
- Descriptive analysis
- Model formulation
- Model development
- Model diagnostics
- Model deployment
- Summary of main findings and future works
- GitHub code link

Your report should include, in the appropriate sections, all the work you did under tasks A) to E) with documentation of the models including the details and explanations outlined above and all relevant estimation results (i.e., model parameters, model results), and interpret the results. Explain your process of obtaining the best model clearly and succinctly as discussed above.

The report is assessed based on the innovation idea (20%), the quality of analysis (30%), the result explanations and discussions (30%), and the report structure and writing (20%). Remember that you must always examine and comment on your results (e.g., which model performs better and why). Additional credit will be awarded for high-quality analysis and writing (present like a professional research paper).