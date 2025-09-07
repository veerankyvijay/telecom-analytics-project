# telecom-analytics-project

Telecom Data Analysis
This project, titled "Telecommunication Data Analysis," is a comprehensive study of a mobile phone dataset. The primary goal was to perform descriptive statistical analysis to identify phone models that meet specific criteria for an informed purchasing decision.

Key Analysis and Findings 📊

Descriptive Statistics: The analysis calculated key metrics such as mean, median, standard deviation, and quartiles for various numerical features including Price, RAM, Int_Mem, and others.

Data Visualization: Histograms were created for features like PC (Primary Camera), FC (Front Camera), Int_Mem (Internal Memory), Bty_Pwr (Battery Power), Depth, and Weight to visualize their distributions and central tendencies.

Logical Conditions & Subsetting: Several logical conditions were created to filter the data based on user preferences. This included identifying phones with high screen resolution, large screen size, good cameras, high memory/power, and a slim/lightweight design.

Final Recommendation: By combining all the logical conditions, a final subset of 6 phone models was identified that met all the specified criteria.

Variability Analysis: The ratio of standard deviation to the mean (Coefficient of Variation) was calculated for all numerical features to assess their relative variability. The results showed that Int_Mem and Price had the highest variability, indicating a wide range of values in the dataset for these features.

Technologies & Packages Used 🛠️

Python: The core programming language used for the analysis.

Pandas: A powerful library for data manipulation and analysis. It was used to load the dataset, create new features, calculate descriptive statistics, and subset the data based on conditions.

Matplotlib: A plotting library used to create and customize the histograms to visualize data distributions.

Jupyter Notebook: The interactive environment where the code was written and executed
