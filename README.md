# pycrimeprediction
[![codecov](https://codecov.io/gh/DSCI-310-2024/pycrimeprediction/graph/badge.svg?token=GA8l3cBDjy)](https://codecov.io/gh/DSCI-310-2024/pycrimeprediction)

```pycrimeprediction``` is the Python package developed by DSCI 301 Group 10. It provides users with the functionality to efficiently load and store dataset files in CSV format using either a URL link or a local file path. Additionally, it offers tools for analyzing crime datasets, particularly those uploaded to the San Francisco Police Department, and performing logistic regression analysis on them.

Our package is different than many of the other packges that's out there! To name a few, some of the package you might have see or heard before.
1. Pandas: The most direct comparison, Pandas provides comprehensive data manipulation capabilities. Our package provides a more sophisticated analytics by extending the functions' abilities. The functions we have in the package can easily import the dataset with a similar format, identify whether the incident is criminal or not, and distinguish the time period.
2. Scikit-Learn: A powerful tool for machine learning. Unlike Scikit-Learn, which is solely focused on modeling, our package provides tools that assist in the following model results incluidng returning the necessary coefficients of the variables and getting validation scores.

   
Overall, our package streamlines the process by bypassing the need to perform logistic regression manually. When you utilize our package, you can forego the entire logistic regression process and simply import it, enabling you to incorporate other models such as decision trees and SVM RBF for comparison of results.

## Installation

```bash
$ pip install pycrimeprediction
```

## Usage

`pycrimeprediction` can be used to analyze data related to crime rates.

Below is a usage example of two of our functions:

```python
from pycrimeprediction.read_save_data import read_save_data
from pycrimeprediction.perform_analysis import perform_analysis

input_path = "url-for-data.csv"
output_path = "saved-data-to-file.csv"

#Read data and split into examples and labels
df = read_save_data(input_path, output_path)
X = df.iloc[:, 0:-1]
y = df.iloc[:, -1]

#Print Cross-validation results for the Logistic Regression classifier
print(perform_analysis(X,y))
```

## Contributing

Interested in contributing? Check out the contributing guidelines. Please note that this project is released with a Code of Conduct. By contributing to this project, you agree to abide by its terms.

## License

`pycrimeprediction` was created by Cassandra Zhang, Pragya Singhal, James He, and Ethan Kenny. It is licensed under the terms of the MIT license.

## Credits

`pycrimeprediction` was created with [`cookiecutter`](https://cookiecutter.readthedocs.io/en/latest/) and the `py-pkgs-cookiecutter` [template](https://github.com/py-pkgs/py-pkgs-cookiecutter).
