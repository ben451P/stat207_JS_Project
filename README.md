# Stat 207 James Scholars Deliverable, Fall Semester 2025

## Project Abstract

This data analysis explores the correlation between the amount of itme spent on lecture and the percentage of questions students answer correctly on the online platform Santa using data gathered in the EdNet dataset. The analysis explores key statistics in the dataset, then utilizes various regression models to determine a correlation between the amount of time spent on lecture and the percentage of questions answered correctly. In the data analysis phase, this analysis most notably finds that the majority of students that use the Santa platform detailed in the dataset do not answer many questions or watch many lectures, most likely due to the expiration of the free trial that the platform offers. Through the regression models, it can be determined that there does not appear to be a correlation between time spent on lectures and student performance.


## Installation and Setup

Clone the repository.

```bash
git clone https://github.com/UIUC-DSC/team-fivecasters
cd team-fivecasters
```

After cloning, create a folder named "dataset" and insert it into the root directory. This project will use the EdNet dataset, which can be found for download at the following links.

1. Main student data: [Here](https://bit.ly/ednet-kt3)
2. Content Data: [Here](https://bit.ly/ednet-content)

Make sure that the data is inserted in the format of the project structure as described below.

Once the dataset is inserted, install requirements.txt on the python version **3.11.4**.
Creating a virtual enviornment is recommended.

```bash
pip install -r requirements.txt
```


## Project Structure

```
├── dataset # all of the code used for processing
│   ├── lectures.csv
│   └── questions.csv
│   ├── KT3                              # Main dataset folders
├── report
│   ├── data_analysis.ipynb              
│   ├── data_cleaning.ipynb              
│   └── data_exploration.ipynb            
├── .gitignore 
├── README.md 
└── requirements.txt 
```


## Running the Project

When running the project, run the python jupyter notebooks in the following order.

1. Data exploration
2. Data cleaning
3. Data analysis


## Notebook Descriptions

### Data Exploration

This section seeks to gather key statistics of the dataset and identify trends that may affect later analysis. The section finds certain lectures to be missing video legnths, and determines that more tenured users, consisting of around 5% of the dataset, would be dropped from the data analysis. However, due to variant video times of lectures, it was decided to drop these data points to utilize total lecture time, which may affect the analysis by focusing primarily on newer students. It further finds that the majority of students only have around 20 lines of information logged for their account. This is hypothesized to be due to the free trial, indicating that the majority of users try the free trial but choose not to pay for the full version of the app to continue learning.

### Data Cleaning

This section performs the data cleaning in the format described in the data exploration notebook. This section describes the cleaned format of the data, and performs the necessary actions on the original data to get it into this format.

### Data Analysis

This section performs the regression analysis on the data in order to answer the question: Does there exist a relationship between the amount of time a student spends on a lecture and the percentage of questions they answer correctly. This section tests a linear regression, logistic regression and a binomial generalized linear model. Through visualization of the data, it can be seen that most of the data points are concentrated near low lecture times with varying percentages of questions answered correctly. Ultimately, all three models fail to establish a meaningful relationship in the data, indicating a lack of a linear relationship between the two data points. However, the RMSE has a surprisingly low value of around .019 all three times, indicating that the majority of data points clustered on the left side of the graph are clusted around this middle percentage of 60-70% which the models then plot a line through.


## Limitations and Future Directions

This findings of this analysis face heavy limitations in generalizability due to the singular source of data for the dataset. Furthermore, the dropping of older users of the app may have an effect in the regression analysis performed on the data. Students may also not take answering questions or watching lectures seriously as it does not directly affect their grades in school, as Santa is a supplementary learning platform. Future analysis on similar questions should focus on a platform directly used in school ciriculumns that keeps older data files instead of dropping information on older materials provided by the platform.


## Citations

Choi, Y., Lee, Y., Shin, D., Cho, J., Park, S., Lee, S., Baek, J., Bae, C., Kim, B., & Heo, J. (2020). EdNet: A Large-Scale Hierarchical Dataset in Education. ArXiv:1912.03072 [Cs]. https://arxiv.org/abs/1912.03072

McKinney, W., & the pandas development team. (2020). pandas-dev/pandas: Pandas (Version 2.2.0) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.10537285

Harris, C. R., Millman, K. J., van der Walt, S. J., Gommers, R., Virtanen, P., et al. (2020). Array programming with NumPy. Nature. https://doi.org/10.1038/s41586-020-2649-2

Hunter, J. D. (2007). Matplotlib: A 2D graphics environment. Computing in Science & Engineering, 9(3), 90–95. https://doi.org/10.1109/MCSE.2007.55

Waskom, M., Botvinnik, O., O’Kane, D., Hobson, P., Lukauskas, S., Gemperline, D. C., Augspurger, T., Halchenko, Y., Cole, J. B., Warmenhoven, J., et al. (2017). seaborn [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.883859

Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., Blondel, M., Prettenhofer, P., Weiss, R., Dubourg, V., Vanderplas, J., Passos, A., Cournapeau, D., Brucher, M., Perrot, M., & Duchesnay, E. (2011). Scikit-learn: Machine learning in Python. Journal of Machine Learning Research, 12, 2825–2830.

Seabold, S., & Perktold, J. (2010). statsmodels: Econometric and statistical modeling with Python. In Proceedings of the 9th Python in Science Conference. 